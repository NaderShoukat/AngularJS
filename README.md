define([
    'text!templates/notifications/index.html',
    'collections/NotificationsCollection',
    'views/notifications/navbar'
], function(indexTemplate, NotificationsCollection, NavbarView) {
    var NotificationsIndexView = Backbone.View.extend({
        el: '#main-content',
        template: _.template(indexTemplate),
        initialize: function() {
            this.collection = new NotificationsCollection();
            this.listenTo(this.collection, 'reset', this.renderGrid);
            this.render();
            this.collection.fetch({reset: true});
        },
        render: function() {
            this.$el.html(this.template());
            this.navbar = new NavbarView({ collection: this.collection });
            this.$('.navbar').html(this.navbar.render().el);
        },
        renderGrid: function() {
            var $tbody = this.$('tbody').empty();
            this.collection.each(function(notification) {
                $tbody.append(
                    `<tr data-id="${notification.id}">
                        <td>${notification.get('title')}</td>
                        <td>${notification.get('message')}</td>
                        <td>${notification.get('type')}</td>
                        <td>${notification.get('date')}</td>
                    </tr>`
                );
            });
        }
    });
    return NotificationsIndexView;
});
