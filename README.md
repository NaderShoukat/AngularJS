angular.module('dataservices.notificationDataService', [])
  .factory('notificationDataService', function($http) {
    var baseUrl = '/Notification'; // adjust route if needed

    return {
      // Get all notifications
      download: function(successCallback, failureCallback) {
        var promise = $http.get(baseUrl + '?format=json');
        promise.then(function(response) {
          successCallback(response.data);
        }, failureCallback);
      },
      // Get by id
      getById: function(id, successCallback, failureCallback) {
        var promise = $http.get(baseUrl + '/' + id + '?format=json');
        promise.then(function(response) {
          successCallback(response.data);
        }, failureCallback);
      },
      // Create
      create: function(data, successCallback, failureCallback) {
        var promise = $http.post(baseUrl, data);
        promise.then(successCallback, failureCallback);
      },
      // Update
      update: function(id, data, successCallback, failureCallback) {
        var promise = $http.put(baseUrl + '/' + id, data);
        promise.then(successCallback, failureCallback);
      },
      // Delete
      remove: function(id, successCallback, failureCallback) {
        var promise = $http.delete(baseUrl + '/' + id);
        promise.then(successCallback, failureCallback);
      }
    };
  });



angular.module('notifications').controller('NotificationsController',
  function($scope, notificationDataService) {
    $scope.notifications = [];

    // Load notifications
    function load() {
      notificationDataService.download(function(data) {
        $scope.notifications = data;
      }, function(error) {
        alert('Error loading notifications');
      });
    }
    load();

    // Add Notification
    $scope.add = function(newNotification) {
      notificationDataService.create(newNotification, function() {
        load();
      });
    };

    // Update Notification
    $scope.update = function(notification) {
      notificationDataService.update(notification.id, notification, function() {
        load();
      });
    };

    // Delete Notification
    $scope.remove = function(id) {
      notificationDataService.remove(id, function() {
        load();
      });
    };
  });





using System.Collections.Generic;
using System.Web.Mvc;
using YourProject.Models; // adjust as needed

namespace YourProject.Controllers
{
    public class NotificationsController : Controller
    {
        static List<Notification> notifications = new List<Notification>
        {
            new Notification { Id = 1, Message = "Test Notification", Type = "Info" }
        };

        [HttpGet]
        public JsonResult Index()
        {
            return Json(notifications, JsonRequestBehavior.AllowGet);
        }

        [HttpPost]
        public JsonResult Create(Notification notification)
        {
            notification.Id = notifications.Count + 1;
            notifications.Add(notification);
            return Json(notification);
        }

        [HttpPut]
        public JsonResult Update(int id, Notification notification)
        {
            var n = notifications.Find(x => x.Id == id);
            if (n != null)
            {
                n.Message = notification.Message;
                n.Type = notification.Type;
            }
            return Json(n);
        }

        [HttpDelete]
        public JsonResult Delete(int id)
        {
            notifications.RemoveAll(x => x.Id == id);
            return Json(true);
        }
    }
    public class Notification
    {
        public int Id { get; set; }
        public string Message { get; set; }
        public string Type { get; set; }
    }
}



