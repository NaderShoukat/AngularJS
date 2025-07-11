define([], function() {
    var notificationsRouter = Backbone.Router.extend({
        routes: {
            "notifications": "showNotifications",
            "notifications/new": "createNotification",
            "notifications/edit/:id": "editNotification"
            // add more as needed
        },

        showNotifications: function() {
            // load notifications grid/view
        },
        createNotification: function() {
            // load create notification view
        },
        editNotification: function(id) {
            // load edit notification view
        }
    });

    return new notificationsRouter();
});
