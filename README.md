angular.module('app').controller('NotificationsController', function($scope, notificationDataService) {
    // List all notifications
    $scope.notifications = [];
    notificationDataService.getAll().then(function(res) {
        $scope.notifications = res.data;
    });

    // Add notification
    $scope.addNotification = function(notification) {
        notificationDataService.create(notification).then(function() {
            // Reload list or redirect
        });
    };

    // Edit notification
    $scope.editNotification = function(notification) {
        $scope.currentNotification = angular.copy(notification);
    };

    // Update notification
    $scope.updateNotification = function(notification) {
        notificationDataService.update(notification).then(function() {
            // Reload list or redirect
        });
    };

    // Delete notification
    $scope.deleteNotification = function(id) {
        notificationDataService.delete(id).then(function() {
            // Reload list
        });
    };
});
