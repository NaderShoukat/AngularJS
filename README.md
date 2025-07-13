<h2>Manage Notifications</h2>
<button class="new-notification">New Notification</button>
<table>
    <thead>
        <tr>
            <th>Title</th>
            <th>Message</th>
            <th>Type</th>
            <th>Date</th>
            <th>Actions</th>
        </tr>
    </thead>
    <tbody>
        <% _.each(notifications, function(n) { %>
            <tr>
                <td><%= n.title %></td>
                <td><%= n.message %></td>
                <td><%= n.type %></td>
                <td><%= n.date %></td>
                <td>
                    <button class="edit-notification" data-id="<%= n.id %>">Edit</button>
                    <button class="delete-notification" data-id="<%= n.id %>">Delete</button>
                </td>
            </tr>
        <% }); %>
    </tbody>
</table>
