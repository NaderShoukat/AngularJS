var css = `
    <style>
        .notif-table-container {
            background: #fff;
            border-radius: 10px;
            margin: 32px 0 0 0;
            padding: 20px 16px 36px 16px;
            box-shadow: 0 4px 18px rgba(80,80,120,0.12);
            max-width: 1000px;
            margin-left: auto;
            margin-right: auto;
        }
        .notif-title-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 16px;
        }
        .notif-title-row h2 {
            font-size: 2.2rem;
            font-weight: 700;
            margin: 0;
            color: #251782;
        }
        .notif-actions-group {
            display: flex;
            gap: 8px;
            align-items: center;
        }
        .notif-add-btn {
            background: #247fff;
            color: #fff;
            padding: 8px 26px;
            border: none;
            border-radius: 7px;
            font-size: 1.1rem;
            font-weight: 600;
            transition: background 0.2s;
        }
        .notif-add-btn:hover {
            background: #0f5dc9;
        }
        .notif-history-btn {
            background: #5c53e6;
            color: #fff;
            padding: 8px 22px;
            border: none;
            border-radius: 7px;
            font-size: 1.1rem;
            font-weight: 600;
            transition: background 0.2s;
        }
        .notif-history-btn:hover {
            background: #352d99;
        }
        .notif-search {
            padding: 8px 12px;
            border-radius: 6px;
            border: 1px solid #d9d9d9;
            font-size: 1.06rem;
            width: 160px;
            margin-left: 8px;
        }
        table.notif-table {
            width: 100%;
            border-collapse: collapse;
        }
        table.notif-table th, table.notif-table td {
            text-align: left;
            padding: 10px 10px;
        }
        table.notif-table th {
            background: #fafafa;
            font-size: 1.08rem;
            font-weight: 700;
            letter-spacing: 0.03rem;
        }
        table.notif-table tr {
            border-bottom: 1px solid #f0f0f0;
        }
        .notif-action-btn {
            margin: 2px 2px;
            padding: 5px 13px;
            border-radius: 6px;
            border: none;
            color: #fff;
            font-size: 1.01rem;
            font-weight: 600;
            cursor: pointer;
            transition: opacity 0.18s;
            display: inline-block;
        }
        .notif-action-edit { background: #247fff; }
        .notif-action-delete { background: #ff3c41; }
        .notif-action-edit:hover { background: #0f5dc9; }
        .notif-action-delete:hover { background: #be2327; }
        .notif-status {
            padding: 5px 18px;
            border-radius: 6px;
            background: #f5f7fa;
            color: #222;
            font-weight: 700;
            display: inline-block;
            min-width: 110px;
            text-align: center;
            font-size: 1.04rem;
        }
    </style>
    `;

    var html = `
    <div class="notif-table-container">
        <div class="notif-title-row">
            <h2>Manage Notifications</h2>
            <div class="notif-actions-group">
                <button class="notif-add-btn" onclick="window.location.hash='#notifications/create'">Add Notification</button>
                <button class="notif-history-btn">History</button>
                <input class="notif-search" type="text" placeholder="Search..." />
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
                    <td><span class="notif-status">Published</span></td>
                    <td>DC</td>
                    <td>Sarah Khan</td>
                    <td>2025-06-28</td>
                    <td>
                        <button class="notif-action-btn notif-action-edit" onclick="window.location.hash='#notifications/edit/1'">Edit</button>
                        <button class="notif-action-btn notif-action-delete">Delete</button>
                    </td>
                </tr>
                <tr>
                    <td>2</td>
                    <td>Help us improve ETS by filling out the short feedback survey available on the homepage.</td>
                    <td><span class="notif-status">Draft</span></td>
                    <td>DC</td>
                    <td>Usman Iqbal</td>
                    <td>2025-06-30</td>
                    <td>
                        <button class="notif-action-btn notif-action-edit" onclick="window.location.hash='#notifications/edit/2'">Edit</button>
                        <button class="notif-action-btn notif-action-delete">Delete</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
    `;
