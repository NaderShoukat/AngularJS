define([], function() {
    var Notification = Backbone.Model.extend({
        idAttribute: "id",
        defaults: {
            title: "",
            message: "",
            type: "",
            date: ""
        }
    });
    return Notification;
});
