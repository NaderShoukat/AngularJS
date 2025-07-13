define([
    'views/notifications/notificationDatagridView',
    'views/notifications/notificationEditView'
], function(notificationDatagridView, notificationEditView) {
    var notificationsRouter = Backbone.Router.extend({
        routes: {
            "notifications": "showNotifications",
            "notifications/new": "createNotification",
            "notifications/edit/:id": "editNotification"
        },

        showNotifications: function () {
            // Render notifications grid view
            notificationDatagridView.render();
        },

        createNotification: function () {
            notificationEditView.render({ mode: 'create' });
        },

        editNotification: function (id) {
            notificationEditView.render({ mode: 'edit', id: id });
        }
    });

    return new notificationsRouter();
});
