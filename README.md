html page:


<div class="title">
    <h2>Notifications</h2>
</div>
<div>
    <ul>
        <li>System maintenance scheduled for 8pm tonight.</li>
        <li>Your password will expire in 5 days.</li>
        <li>New document uploaded: ProjectPlan.docx</li>
    </ul>
</div>


js:
define([
    'text!templates/notifications/notifications.html'
], function(template) {
    var notificationsView = Backbone.View.extend({
        template: _.template(template),
        initialize: function () { },
        render: function () {
            this.$el.html(this.template());
            return this;
        }
    });
    return notificationsView;
});


router:
define([
    // ... other views ...
    'views/notifications/notificationsView'
], function(
    // ... other views ...
    notificationsView
) {
    var MainRouter = Backbone.Router.extend({
        routes: {
            // ... other routes ...
            'notifications': 'notifications'
        },
        notifications: function () {
            var view = new notificationsView();
            $('.workarea').html(view.render().el); // Render in main work area
        }
    });
    return MainRouter;
});

