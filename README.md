define([], function () {
    var notificationsRouter = Backbone.Router.extend({
        routes: {
            "notifications": "notifications"
        },
        initialize: function () {},
        notifications: function () {
            // Hardcoded data for table rows
            var html = `
                <div class="content">
                    <h2>Manage Notifications</h2>
                    <input type="text" class="search" placeholder="Search..." />
                    <table class="table">
                        <thead>
                            <tr>
                                <th>ID</th>
                                <th>Message</th>
                                <th>Status</th>
                                <th>Type</th>
                                <th>Created By</th>
                                <th>Created Date</th>
                                <th>Action</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>1</td>
                                <td>This is a reminder that all examiners must submit their Quarterly Exam Data by Friday, July 6, 2025.</td>
                                <td><input type="checkbox" checked disabled /></td>
                                <td>DocX</td>
                                <td>On-Demand</td>
                                <td>2025-06-28</td>
                                <td>
                                    <button class="edit-btn">Edit</button>
                                    <button class="delete-btn">Delete</button>
                                </td>
                            </tr>
                            <tr>
                                <td>2</td>
                                <td>Help us improve ETS by filling out the short feedback survey available on the homepage.</td>
                                <td><input type="checkbox" disabled /></td>
                                <td>DocX</td>
                                <td>On-Demand</td>
                                <td>2025-06-28</td>
                                <td>
                                    <button class="edit-btn">Edit</button>
                                    <button class="delete-btn">Delete</button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            `;
            $('.workarea').html(html); // Insert into your main work area
        }
    });
    return notificationsRouter;
});
