

Get Notification History (GET /api/notifications/history):
Response:

[
  {
    "id": 2,
    "notificationId": 2,
    "message": "Help us improve ETS by filling out the short feedback survey available on the homepage.",
    "status": "Draft",
    "type": "DC",
    "createdBy": "Usman Iqbal",
    "createdDate": "2025-06-30",
    "updatedBy": "Usman Iqbal",
    "updatedDate": "2025-07-01"
  },
  {
    "id": 1,
    "notificationId": 2,
    "message": "Help us improve ETS by filling out the short feedback survey available on the homepage.",
    "status": "Queued",
    "type": "DC",
    "createdBy": "Usman Iqbal",
    "createdDate": "2025-06-28",
    "updatedBy": "Sarah Khan",
    "updatedDate": "2025-06-29"
  }
]

////////////////////////////

Get Notification By ID (GET /api/notifications/{id})
Response:
{
  "id": 2,
  "message": "Help us improve ETS by filling out the short feedback survey available on the homepage.",
  "status": "Draft",
  "type": "DC",
  "createdBy": "Usman Iqbal",
  "createdDate": "2025-06-30",
  "startDate": "2025-06-01",
  "endDate": "2025-07-01"
}


/////////////////////
List Notifications (GET /api/notifications)
Response


[
  {
    "id": 1,
    "message": "This is a reminder that all examiners must submit their Quarterly Exam Data by Friday, July 6, 2025.",
    "status": "Published",
    "type": "DC",
    "createdBy": "Sarah Khan",
    "createdDate": "2025-06-28",
    "startDate": "2025-06-01",
    "endDate": "2025-07-06"
  },
  {
    "id": 2,
    "message": "Help us improve ETS by filling out the short feedback survey available on the homepage.",
    "status": "Draft",
    "type": "DC",
    "createdBy": "Usman Iqbal",
    "createdDate": "2025-06-30",
    "startDate": "2025-06-01",
    "endDate": "2025-07-01"
  }
]


/////////////////////////

Edit Notification (PUT /api/notifications/{id})
Request Body:


{
  "message": "Help us improve ETS by filling out the short feedback survey available on the homepage.",
  "status": "Draft",
  "type": "DC",
  "createdBy": "Usman Iqbal",
  "createdDate": "2025-06-30",
  "startDate": "2025-06-01",
  "endDate": "2025-07-01"
}


Response:

{
  "success": true,
  "notification": {
    "id": 2,
    "message": "...",
    "status": "Draft",
    "type": "DC",
    "createdBy": "Usman Iqbal",
    "createdDate": "2025-06-30",
    "startDate": "2025-06-01",
    "endDate": "2025-07-01"
  }
}


//////////////////////////////
Add Notification (POST /api/notifications)
Request Body

{
  "message": "This is a reminder that all examiners must submit their Quarterly Exam Data by Friday, July 6, 2025.",
  "status": "Published",            // Draft, Queued, Published
  "type": "DC",                     // Type string or code
  "createdBy": "Sarah Khan",        // User name or id
  "createdDate": "2025-06-28",      // ISO date string
  "startDate": "2025-06-01",
  "endDate": "2025-07-06"
}


Response

{
  "success": true,
  "notification": {
    "id": 3,
    "message": "...",
    "status": "Published",
    "type": "DC",
    "createdBy": "Sarah Khan",
    "createdDate": "2025-06-28",
    "startDate": "2025-06-01",
    "endDate": "2025-07-06"
  }
}
/////////////////////////////////

