notifications.html:


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


notificationsView.js:
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


notificationsRouter:
define([
    'views/notifications/notificationsView'
], function(notificationsView) {
    var notificationsRouter = Backbone.Router.extend({
        routes: {
            "notifications": "index"
        },
        initialize: function () {},
        index: function () {
            // Render the notifications view in the main work area
            $('.workarea').html(new notificationsView().render().el);
        }
    });
    return notificationsRouter;
});
