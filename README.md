define([
    'text!templates/notifications/edit.html',
    'collections/NotificationsCollection'
], function(editTemplate, NotificationsCollection) {
    var NotificationsEditView = Backbone.View.extend({
        el: '#main-content',
        template: _.template(editTemplate),
        events: {
            "submit #notificationEditForm": "saveNotification"
        },
        initialize: function(options) {
            this.options = options || {};
        },
        render: function(id) {
            var notification = {};
            var action = id ? "Edit" : "New";
            if (id) {
                var self = this;
                var collection = new NotificationsCollection();
                collection.fetch({
                    success: function() {
                        var model = collection.get(id);
                        notification = model ? model.toJSON() : {};
                        self.$el.html(self.template({notification: notification, action: action}));
                    }
                });
            } else {
                this.$el.html(this.template({notification: notification, action: action}));
            }
        },
        saveNotification: function(e) {
            e.preventDefault();
            var attrs = {
                title: this.$('#title').val(),
                message: this.$('#message').val(),
                type: this.$('#type').val(),
                date: this.$('#date').val()
            };
            var id = this.options.id;
            var collection = new NotificationsCollection();
            var model = id ? collection.get(id) : collection.create(attrs, {wait: true});
            if (id) {
                model.save(attrs, {
                    success: function() {
                        window.location.hash = "#notifications";
                    }
                });
            } else {
                collection.create(attrs, {
                    success: function() {
                        window.location.hash = "#notifications";
                    }
                });
            }
        }
    });
    return NotificationsEditView;
});
