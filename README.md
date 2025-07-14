using System.Collections.Generic;
using System.Linq;
using System.Web.Mvc;
using ETSAdminSite.Web.UI.Models; // adjust namespace as needed

namespace ETSAdminSite.Web.UI.Controllers
{
    public class NotificationsController : Controller
    {
        // In-memory list for demo (replace with DB in future)
        private static List<Notification> items = new List<Notification>
        {
            new Notification { id = "1", title = "Server Maintenance", message = "Scheduled maintenance at 2AM.", date = "2024-07-15", type = "info" },
            new Notification { id = "2", title = "Policy Update", message = "Review updated company policies.", date = "2024-07-14", type = "alert" }
        };

        // GET: /Notification
        [HttpGet]
        public JsonResult Index()
        {
            return Json(new { results = items }, JsonRequestBehavior.AllowGet);
        }

        // GET: /Notification/{id}
        [HttpGet]
        public JsonResult GetById(string id)
        {
            var n = items.FirstOrDefault(x => x.id == id);
            return Json(n, JsonRequestBehavior.AllowGet);
        }

        // POST: /Notification
        [HttpPost]
        public JsonResult Create(Notification notification)
        {
            notification.id = (items.Count + 1).ToString();
            items.Add(notification);
            return Json(notification);
        }

        // PUT: /Notification/{id}
        [HttpPut]
        public JsonResult Update(string id, Notification notification)
        {
            var n = items.FirstOrDefault(x => x.id == id);
            if (n != null)
            {
                n.title = notification.title;
                n.message = notification.message;
                n.date = notification.date;
                n.type = notification.type;
            }
            return Json(n);
        }

        // DELETE: /Notification/{id}
        [HttpDelete]
        public JsonResult Delete(string id)
        {
            var n = items.FirstOrDefault(x => x.id == id);
            if (n != null)
            {
                items.Remove(n);
            }
            return Json(new { success = true });
        }
    }

    // Example Model
    public class Notification
    {
        public string id { get; set; }
        public string title { get; set; }
        public string message { get; set; }
        public string date { get; set; }
        public string type { get; set; }
    }
}












angular.module('dataservices.notificationDataService', [])
.factory('notificationDataService', function ($http) {
    var baseUrl = '/Notification';

    return {
        // Get all notifications
        download: function (successCallback, failureCallback) {
            $http.get(baseUrl)
                .then(function (response) {
                    successCallback(response.data.results);
                }, failureCallback);
        },
        // Get by id
        getById: function (id, successCallback, failureCallback) {
            $http.get(baseUrl + '/' + id)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        },
        // Create
        create: function (notification, successCallback, failureCallback) {
            $http.post(baseUrl, notification)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        },
        // Update
        update: function (id, notification, successCallback, failureCallback) {
            $http.put(baseUrl + '/' + id, notification)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        },
        // Delete
        remove: function (id, successCallback, failureCallback) {
            $http.delete(baseUrl + '/' + id)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        }
    };
});








service
angular.module('dataservices.notificationDataService', [])
.factory('notificationDataService', function ($http) {
    var baseUrl = '/Notification';

    return {
        // Get all notifications
        download: function (successCallback, failureCallback) {
            $http.get(baseUrl)
                .then(function (response) {
                    successCallback(response.data.results);
                }, failureCallback);
        },
        // Get by id
        getById: function (id, successCallback, failureCallback) {
            $http.get(baseUrl + '/' + id)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        },
        // Create
        create: function (notification, successCallback, failureCallback) {
            $http.post(baseUrl, notification)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        },
        // Update
        update: function (id, notification, successCallback, failureCallback) {
            $http.put(baseUrl + '/' + id, notification)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        },
        // Delete
        remove: function (id, successCallback, failureCallback) {
            $http.delete(baseUrl + '/' + id)
                .then(function (response) {
                    successCallback(response.data);
                }, failureCallback);
        }
    };
});






cntrl


angular.module('notifications', ['dataservices.notificationDataService'])
.controller('NotificationsCtrl', function ($scope, notificationDataService) {
    $scope.notifications = [];
    $scope.form = {}; // For create/edit
    $scope.error = null;

    // Load all
    function loadAll() {
        notificationDataService.download(
            function (data) { $scope.notifications = data; },
            function (err) { $scope.error = "Failed to load notifications"; }
        );
    }
    loadAll();

    // Add new
    $scope.createNotification = function () {
        notificationDataService.create($scope.form, function (data) {
            $scope.form = {};
            loadAll();
        });
    };

    // Edit (prefill form)
    $scope.editNotification = function (n) {
        $scope.form = angular.copy(n);
    };

    // Update
    $scope.updateNotification = function () {
        notificationDataService.update($scope.form.id, $scope.form, function (data) {
            $scope.form = {};
            loadAll();
        });
    };

    // Delete
    $scope.deleteNotification = function (n) {
        if (confirm("Delete this notification?")) {
            notificationDataService.remove(n.id, function () {
                loadAll();
            });
        }
    };
});






html



<div ng-controller="NotificationsCtrl">
    <h2>Manage Notifications</h2>
    <form ng-submit="form.id ? updateNotification() : createNotification()">
        <input ng-model="form.title" placeholder="Title" required>
        <input ng-model="form.message" placeholder="Message" required>
        <input ng-model="form.date" placeholder="Date" required>
        <input ng-model="form.type" placeholder="Type" required>
        <button type="submit">{{form.id ? 'Update' : 'Create'}}</button>
        <button type="button" ng-click="form={}">Clear</button>
    </form>

    <table>
        <thead>
            <tr>
                <th>Title</th><th>Message</th><th>Type</th><th>Date</th><th>Actions</th>
            </tr>
        </thead>
        <tbody>
            <tr ng-repeat="n in notifications">
                <td>{{n.title}}</td>
                <td>{{n.message}}</td>
                <td>{{n.type}}</td>
                <td>{{n.date}}</td>
                <td>
                    <button ng-click="editNotification(n)">Edit</button>
                    <button ng-click="deleteNotification(n)">Delete</button>
                </td>
            </tr>
        </tbody>
    </table>
    <div ng-if="error">{{error}}</div>
</div>
