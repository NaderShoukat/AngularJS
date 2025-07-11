<div ng-controller="NotificationsController">
    <h2>Notifications</h2>
    <table>
        <tr>
            <th>Title</th>
            <th>Message</th>
            <th>Actions</th>
        </tr>
        <tr ng-repeat="n in notifications">
            <td>{{n.title}}</td>
            <td>{{n.message}}</td>
            <td>
                <button ng-click="editNotification(n)">Edit</button>
                <button ng-click="deleteNotification(n.id)">Delete</button>
            </td>
        </tr>
    </table>
    <button ng-click="showAddForm = true">Add Notification</button>
    <div ng-show="showAddForm">
        <input ng-model="newNotification.title" placeholder="Title" />
        <input ng-model="newNotification.message" placeholder="Message" />
        <button ng-click="addNotification(newNotification)">Save</button>
    </div>
</div>
