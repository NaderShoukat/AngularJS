define([
    'text!templates/notifications/navbar.html'
], function(navbarTemplate) {
    var NavbarView = Backbone.View.extend({
        template: _.template(navbarTemplate),
        events: {
            "click .new-item": "onNew",
            "click .edit": "onEdit",
            "click .delete": "onDelete",
            "click .update-date": "onUpdate"
        },
        render: function() {
            this.$el.html(this.template());
            return this;
        },
        onNew: function(e) {
            e.preventDefault();
            window.location.hash = "#notifications/new";
        },
        onEdit: function(e) {
            e.preventDefault();
            var selected = this.getSelectedId();
            if (selected) {
                window.location.hash = "#notifications/edit/" + selected;
            }
        },
        onDelete: function(e) {
            e.preventDefault();
            var selected = this.getSelectedId();
            if (selected && confirm("Delete this notification?")) {
                // Implement delete logic here
            }
        },
        onUpdate: function(e) {
            e.preventDefault();
            // Optionally reload collection
        },
        getSelectedId: function() {
            // Add logic to get selected notification's ID from grid (e.g., via .selected row)
            return null;
        }
    });
    return NavbarView;
});
