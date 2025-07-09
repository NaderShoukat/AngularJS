angular.module('dataservices.notificationDataService', [])
.factory('notificationDataService', function($http) {
    var baseUrl = 'http://localhost:8080/api/notifications'; // Replace with your actual API base

    return {
        getAll: function() {
            return $http.get(baseUrl);
        },
        getById: function(id) {
            return $http.get(baseUrl + '/' + id);
        },
        create: function(notification) {
            return $http.post(baseUrl, notification);
        },
        update: function(notification) {
            return $http.put(baseUrl + '/' + notification.id, notification);
        },
        delete: function(id) {
            return $http.delete(baseUrl + '/' + id);
        }
    };
});
