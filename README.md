var css = `
    .notif-header-bar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 18px;
        margin-top: 16px;
    }
    .notif-title {
        flex: 1;
        text-align: center;
        font-size: 2rem;
        font-weight: bold;
    }
    .notif-actions {
        display: flex;
        align-items: center;
        gap: 12px;
    }
    .add-btn {
        background: #1976d2;
        color: #fff;
        font-weight: 500;
        padding: 7px 18px;
        border-radius: 7px;
        margin-right: 6px;
        border: none;
        cursor: pointer;
        transition: background 0.2s;
    }
    .add-btn:hover { background: #155fa0; }
    .notif-search {
        padding: 7px 12px;
        border-radius: 7px;
        border: 1px solid #ddd;
        min-width: 170px;
    }
    .notif-table {
        width: 100%;
        border-collapse: collapse;
        background: #fff;
        border-radius: 10px;
        overflow: hidden;
        font-size: 1rem;
        margin-top: 5px;
    }
    .notif-table th, .notif-table td {
        padding: 14px 10px;
        text-align: left;
        border-bottom: 1px solid #f1f1f1;
    }
    .notif-table th {
        background: #fafafa;
        font-weight: 700;
    }
    .action-btn {
        margin-right: 6px;
        padding: 4px 14px;
        border-radius: 6px;
        border: none;
        font-size: 1rem;
        cursor: pointer;
        transition: background 0.2s;
    }
    .btn-primary { background: #1976d2; color: #fff; }
    .btn-primary:hover { background: #155fa0; }
    .btn-danger { background: #ff5252; color: #fff; }
    .btn-danger:hover { background: #d32f2f; }
    `;

    // Hardcoded HTML
    var html = `
    <div class="notif-header-bar">
        <div class="notif-title">Manage Notifications</div>
        <div class="notif-actions">
            <button class="btn btn-primary add-btn" id="addNotifBtn">Add Notification</button>
            <input type="text" class="notif-search" placeholder="Search...">
        </div>
    </div>
    <table class="notif-table">
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
                <td><input type="checkbox" checked disabled></td>
                <td>DC</td>
                <td>On-Demand</td>
                <td>2025-06-28</td>
                <td>
                    <button class="btn btn-primary action-btn" onclick="window.location.hash='#notifications/edit/1'">Edit</button>
                    <button class="btn btn-danger action-btn">Delete</button>
                </td>
            </tr>
            <tr>
                <td>2</td>
                <td>Help us improve ETS by filling out the short feedback survey available on the homepage.</td>
                <td><input type="checkbox" disabled></td>
                <td>DC</td>
                <td>On-Demand</td>
                <td>2025-06-28</td>
                <td>
                    <button class="btn btn-primary action-btn" onclick="window.location.hash='#notifications/edit/2'">Edit</button>
                    <button class="btn btn-danger action-btn">Delete</button>
                </td>
            </tr>
        </tbody>
    </table>
    `;

    $('.workarea').html('<style>' + css + '</style>' + html);

    // Add routing for Add Notification
    setTimeout(function() {
        $('#addNotifBtn').off('click').on('click', function () {
            window.location.hash = '#notifications/create';
        });
    }, 100); // slight delay for DOM
