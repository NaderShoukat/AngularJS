<div>
    <a href="#notifications">Notifications</a> &gt; <%= action %> Notification
</div>
<div class="title">
    <h2><%= action %> Notification</h2>
</div>

<form class="blue" id="notificationEditForm" action="" method="POST">
    <div class="row-fluid blue span12">
        <div class="row-fluid">
            <label class="span3" for="title">Title:</label>
            <input id="title" name="title" type="text" class="span6" value="<%= notification.title %>"/>
        </div>
        <div class="row-fluid">
            <label class="span3" for="message">Message:</label>
            <input id="message" name="message" type="text" class="span6" value="<%= notification.message %>"/>
        </div>
        <div class="row-fluid">
            <label class="span3" for="type">Type:</label>
            <input id="type" name="type" type="text" class="span6" value="<%= notification.type %>"/>
        </div>
        <div class="row-fluid">
            <label class="span3" for="date">Date:</label>
            <input id="date" name="date" type="date" class="span6" value="<%= notification.date %>"/>
        </div>
        <div class="row-fluid">
            <button type="submit" class="btn btn-primary">Save</button>
            <a href="#notifications" class="btn">Cancel</a>
        </div>
    </div>
</form>
