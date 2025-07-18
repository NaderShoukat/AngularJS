var notificationsRouter = Backbone.Router.extend({
    routes: {
        "notifications": "notifications",                // List/index
        "notifications/create": "createNotification",    // Create
        "notifications/edit/:id": "editNotification"     // Edit
    },

    notifications: function() {
        // Hardcoded notifications data
        var notifications = [
            {
                id: 1,
                message: "This is a reminder that all examiners must submit their Quarterly Exam Data by Friday, July 6, 2025.",
                status: true,
                type: "DocX",
                createdBy: "On-Demand",
                createdDate: "2025-06-28"
            },
            {
                id: 2,
                message: "Help us improve ETS by filling out the short feedback survey available on the homepage.",
                status: false,
                type: "DocX",
                createdBy: "On-Demand",
                createdDate: "2025-06-28"
            }
        ];

        // Build HTML table rows
        var rows = notifications.map(function(n) {
            return `
                <tr>
                    <td>${n.message}</td>
                    <td><input type="checkbox" ${n.status ? "checked" : ""} disabled /></td>
                    <td>${n.type}</td>
                    <td>${n.createdBy}</td>
                    <td>${n.createdDate}</td>
                    <td>
                        <button class="edit-btn" onclick="window.location.hash='notifications/edit/${n.id}'">Edit</button>
                        <button class="delete-btn">Delete</button>
                    </td>
                </tr>
            `;
        }).join('');

        // Full HTML
        var html = `
            <div class="content">
                <h2>Manage Notifications</h2>
                <a href="#notifications/create" class="save-btn">Add Notification</a>
                <input type="text" class="search" placeholder="Search..." />
                <table class="table">
                    <thead>
                        <tr>
                            <th>Message</th>
                            <th>Status</th>
                            <th>Type</th>
                            <th>Created By</th>
                            <th>Created Date</th>
                            <th>Action</th>
                        </tr>
                    </thead>
                    <tbody>
                        ${rows}
                    </tbody>
                </table>
            </div>
        `;
        $('.workarea').html(html);
    },

    createNotification: function() {
        // Create Notification mockup
        var html = `
            <div class="form-container">
                <h2>Add Notification</h2>
                <form>
                    <label>Message</label>
                    <textarea rows="3" required></textarea>

                    <label>Type</label>
                    <select required>
                        <option value="">Select type</option>
                        <option value="Template">Template</option>
                        <option value="One-time">One-time</option>
                        <option value="Ongoing" selected>Ongoing</option>
                        <option value="Release notes">Release notes</option>
                    </select>

                    <label>Status</label>
                    <select required>
                        <option value="">Select Status</option>
                        <option value="draft">Draft</option>
                        <option value="queued">Queued</option>
                        <option value="published" selected>Published</option>
                    </select>

                    <label>Created By</label>
                    <select required>
                        <option value="">Select User</option>
                        <option value="name1">Name1</option>
                        <option value="name2">Name2</option>
                    </select>

                    <label>Start date</label>
                    <input type="date" required />
                    <label>End date</label>
                    <input type="date" required />

                    <br>
                    <button type="submit" class="save-btn">Submit Notification</button>
                    <button type="button" class="save-btn" onclick="window.location.hash='notifications'">Cancel</button>
                </form>
            </div>
        `;
        $('.workarea').html(html);
    },

    editNotification: function(id) {
        // Edit Notification mockup (loads hardcoded data for demo)
        var n = {
            id: id,
            message: "This is a reminder that all examiners must submit their Quarterly Exam Data by Friday, July 6, 2025.",
            status: true,
            type: "DocX",
            createdBy: "On-Demand",
            createdDate: "2025-06-28"
        };
        var html = `
            <div class="form-container">
                <h2>Edit Notification</h2>
                <form>
                    <label>Message</label>
                    <textarea rows="3" required>${n.message}</textarea>

                    <label>Type</label>
                    <select required>
                        <option value="DocX" selected>DocX</option>
                        <option value="Template">Template</option>
                    </select>

                    <label>Status</label>
                    <select required>
                        <option value="active" ${n.status ? "selected" : ""}>Active</option>
                        <option value="inactive" ${!n.status ? "selected" : ""}>Inactive</option>
                    </select>

                    <label>Created By</label>
                    <input type="text" value="${n.createdBy}" required />

                    <label>Created Date</label>
                    <input type="date" value="${n.createdDate}" required />

                    <br>
                    <button type="submit" class="save-btn">Update Notification</button>
                    <button type="button" class="save-btn" onclick="window.location.hash='notifications'">Cancel</button>
                </form>
            </div>
        `;
        $('.workarea').html(html);
    }
});

// Initialize the router (do this in your main app JS)
var router = new notificationsRouter();
Backbone.history.start();
