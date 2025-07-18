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
            <tr ng-repeat="notification in notifications">
                <td>{{notification.id}}</td>
                <td>{{notification.message}}</td>
                <td>
                    <input type="checkbox" ng-checked="notification.status" disabled />
                </td>
                <td>{{notification.type}}</td>
                <td>{{notification.createdBy}}</td>
                <td>{{notification.createdDate}}</td>
                <td>
                    <button class="edit-btn">Edit</button>
                    <button class="delete-btn">Delete</button>
                </td>
            </tr>
        </tbody>
    </table>
</div>
