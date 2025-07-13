notifications: function(callback) {
    new NotificationsCollection().fetch({
        success: function(collection) {
            callback(null, collection);
        }
    });
},
window.notificationsCollection = new NotificationsCollection(results.notifications.models);
