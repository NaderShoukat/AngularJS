history: function () {
    var css = `
    <style>
        .history-container {
            background: #fff;
            border-radius: 10px;
            margin: 32px 0 0 0;
            padding: 24px 18px 38px 18px;
            box-shadow: 0 4px 18px rgba(80,80,120,0.11);
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }
        .history-title-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 16px;
        }
        .history-title-row h2 {
            font-size: 2.1rem;
            font-weight: 700;
            margin: 0;
            color: #251782;
        }
        .history-back-btn {
            background: #247fff;
            color: #fff;
            padding: 8px 22px;
            border: none;
            border-radius: 7px;
            font-size: 1.08rem;
            font-weight: 600;
            transition: background 0.2s;
            margin-right: 8px;
        }
        .history-back-btn:hover {
            background: #0f5dc9;
        }
        .history-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 14px;
        }
        .history-table th, .history-table td {
            text-align: left;
            padding: 9px 10px;
        }
        .history-table th {
            background: #fafafa;
            font-size: 1.08rem;
            font-weight: 700;
            letter-spacing: 0.03rem;
        }
        .history-table tr {
            border-bottom: 1px solid #f0f0f0;
        }
        .history-status {
            padding: 4px 15px;
            border-radius: 5px;
            background: #f1f4fa;
            color: #333;
            font-weight: 600;
            display: inline-block;
            min-width: 85px;
            text-align: center;
            font-size: 1.01rem;
        }
        .history-user {
            color: #251782;
            font-weight: 700;
        }
        .history-date {
            color: #4a4a4a;
            font-size: 0.97rem;
        }
        .history-msg {
            font-size: 1.01rem;
        }
    </style>
    `;
    var html = `
    <div class="history-container">
        <div class="history-title-row">
            <h2>Notification History (Last 2 Years)</h2>
            <button class="history-back-btn" onclick="window.location.hash='#notifications'">&larr; Back</button>
        </div>
        <table class="history-table">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Date & Time</th>
                    <th>User</th>
                    <th>Status</th>
                    <th>Message (Summary)</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>1</td>
                    <td class="history-date">2024-07-05 09:15</td>
                    <td class="history-user">Sarah Khan</td>
                    <td><span class="history-status">Published</span></td>
                    <td class="history-msg">Quarterly Exam Data notification created and published.</td>
                </tr>
                <tr>
                    <td>2</td>
                    <td class="history-date">2024-12-02 14:22</td>
                    <td class="history-user">Usman Iqbal</td>
                    <td><span class="history-status">Draft</span></td>
                    <td class="history-msg">Draft saved for feedback survey notification.</td>
                </tr>
                <tr>
                    <td>3</td>
                    <td class="history-date">2025-01-08 10:40</td>
                    <td class="history-user">Sarah Khan</td>
                    <td><span class="history-status">Published</span></td>
                    <td class="history-msg">Feedback survey notification published.</td>
                </tr>
                <tr>
                    <td>4</td>
                    <td class="history-date">2025-05-19 17:30</td>
                    <td class="history-user">Usman Iqbal</td>
                    <td><span class="history-status">Updated</span></td>
                    <td class="history-msg">Message content updated for quarterly data reminder.</td>
                </tr>
                <tr>
                    <td>5</td>
                    <td class="history-date">2025-06-28 13:16</td>
                    <td class="history-user">Sarah Khan</td>
                    <td><span class="history-status">Published</span></td>
                    <td class="history-msg">Minor typo fixed in published notification.</td>
                </tr>
            </tbody>
        </table>
    </div>
    `;
    $('.workarea').html(css + html);
},
