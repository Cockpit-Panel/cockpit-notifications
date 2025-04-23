# Cockpit Notifications

This repository manages a simple JSON feed for global notifications displayed in the Cockpit Panel or related apps.

## 📢 Notification Format

Each notification entry contains:

- `id`: Unique integer
- `title`: Short headline
- `message`: Main body text
- `timestamp`: ISO 8601 formatted date/time
- `icon`: Bootstrap icon class (e.g. `bi-code-slash`, `bi-telegram`)
- `url`: Link users can follow (optional)

---

## 🧾 Example JSON

```json
{
  "notifications": [
    {
      "id": 1,
      "title": "CP2 Under Development",
      "message": "Cockpit v2 is under development.",
      "timestamp": "2023-07-12T15:30:00Z",
      "icon": "bi-code-slash",
      "url": "https://cockpit.lol/"
    },
    {
      "id": 2,
      "title": "Contact @ianwoneill",
      "message": "Contact @ianwoneill for pre-orders.",
      "timestamp": "2023-07-11T09:15:00Z",
      "icon": "bi-telegram",
      "url": "https://t.me/ianwoneill"
    },
    {
      "id": 3,
      "title": "Buy me a Coffee",
      "message": "Buy me a drink: Cashapp £ianwoneill",
      "timestamp": "2023-07-10T18:45:00Z",
      "icon": "bi-cup-hot-fill",
      "url": "https://cash.app/ianwoneill"
    }
  ]
}
```

---

## 🛠 Adding a New Notification

1. Increment the `id` by 1.
2. Use a short, descriptive `title`.
3. Keep `message` concise (ideally under 150 characters).
4. Format the `timestamp` in **UTC ISO format**.
5. Use [Bootstrap Icons](https://icons.getbootstrap.com/) for `icon`.
6. Make sure URLs are valid and begin with `https://`.

---

## 🔁 Updating

Once updated:
```bash
git add notifications.json
git commit -m "Add new notification: [title]"
git push
```

---

## 🔔 Use Case

This JSON can be polled by your apps or panels to show live announcements, update notices, or promo alerts.

--- 

Want to automate expiration of old messages or limit to N recent ones? You can build a simple script or backend cron job to trim the list automatically.
