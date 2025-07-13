namespace ETSAdminSite.Web.UI.Models
{
    public class Notification
    {
        public string id { get; set; }
        public string title { get; set; }
        public string message { get; set; }
        public string date { get; set; }
        public string type { get; set; }
    }
}

using System.Collections.Generic;
using System.Linq;
using System.Web.Mvc;
using ETSAdminSite.Web.UI.Models;
using Newtonsoft.Json;

namespace ETSAdminSite.Web.UI.Controllers
{
    public class NotificationsController : Controller
    {
        // Static in-memory notifications list (simulates database)
        private static List<Notification> items = new List<Notification>
        {
            new Notification { id = "1", title = "Server Maintenance", message = "Scheduled maintenance at 2AM.", date = "2024-07-15", type = "info" },
            new Notification { id = "2", title = "Policy Update", message = "Review updated company policies.", date = "2024-07-14", type = "alert" }
        };

        // GET: /Notifications/Index
        [HttpGet]
        public ActionResult Index(string callback)
        {
            // For JSONP support, like your current controllers
            var json = JsonConvert.SerializeObject(new { d = new { results = items } });
            return Content($"{callback}({json})", "application/javascript");
        }

        // GET: /Notifications/GetById?id=1
        [HttpGet]
        public ActionResult GetById(string callback, string id)
        {
            var notification = items.FirstOrDefault(n => n.id == id);
            var json = JsonConvert.SerializeObject(new { d = notification });
            return Content($"{callback}({json})", "application/javascript");
        }

        // POST: /Notifications/Create
        [HttpPost]
        public ActionResult Create(Notification notification)
        {
            notification.id = (items.Count + 1).ToString();
            items.Add(notification);
            return Json(new { success = true, notification });
        }

        // POST: /Notifications/Update
        [HttpPost]
        public ActionResult Update(Notification notification)
        {
            var existing = items.FirstOrDefault(n => n.id == notification.id);
            if (existing != null)
            {
                existing.title = notification.title;
                existing.message = notification.message;
                existing.date = notification.date;
                existing.type = notification.type;
            }
            return Json(new { success = true, notification });
        }

        // POST: /Notifications/Delete
        [HttpPost]
        public ActionResult Delete(string id)
        {
            var existing = items.FirstOrDefault(n => n.id == id);
            if (existing != null)
            {
                items.Remove(existing);
            }
            return Json(new { success = true });
        }
    }
}
