<h2><% if (notification.id) { %>Edit<% } else { %>Create<% } %> Notification</h2>
<form>
    <% if (notification.id) { %>
        <input type="hidden" name="id" value="<%= notification.id %>" />
    <% } %>
    <label>Title: <input type="text" name="title" value="<%= notification.title || '' %>"></label><br>
    <label>Message: <input type="text" name="message" value="<%= notification.message || '' %>"></label><br>
    <label>Type: <input type="text" name="type" value="<%= notification.type || '' %>"></label><br>
    <label>Date: <input type="date" name="date" value="<%= notification.date || '' %>"></label><br>
    <button type="submit">Save</button>
</form>
