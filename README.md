define([
    'views/notifications/index',
    'views/notifications/edit'
], function(IndexView, EditView) {
    var NotificationsRouter = Backbone.Router.extend({
        routes: {
            "notifications": "showNotifications",
            "notifications/new": "createNotification",
            "notifications/edit/:id": "editNotification"
        },
        showNotifications: function() {
            var view = new IndexView();
            view.render();
        },
        createNotification: function() {
            var view = new EditView();
            view.render();
        },
        editNotification: function(id) {
            var view = new EditView({id: id});
            view.render(id);
        }
    });
    return new NotificationsRouter();
});
