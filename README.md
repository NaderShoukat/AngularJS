notifications: function(callback) {
    new NotificationsCollection().fetch({
        success: function(collection) {
            callback(null, collection);
        }
    });
},
