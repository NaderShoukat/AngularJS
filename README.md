define(['models/Notification'], function(Notification) {
    var NotificationCollection = Backbone.Collection.extend({
        model: Notification,
        url: '/api/notifications' // Update if different
    });
    return NotificationCollection;
});
