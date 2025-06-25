# 📋 Telegram Attendance Bot

A lightweight Telegram bot built using **Google Apps Script** and **Google Sheets** to manage attendance tracking for group-based activities such as classes, youth groups, or events. This bot can mark attendees, show summaries, and clear attendance logs—all from a simple chat interface.

---

## 🚀 Features

- Mark group attendance using `/markpresent#` command  
- Automatically logs names and timestamps to Google Sheets  
- Stores data per group (e.g., Group 0–3) and in a combined "All" sheet  
- View daily attendance summary using `/summary`  
- Clear attendance for all groups using `/clear`  
- Webhook-based response system using Google Apps Script Web App

---

## 🧰 Tech Stack

- **Telegram Bot API**  
- **Google Apps Script** (serverless backend)  
- **Google Sheets** (cloud database)  

---

## 📁 Setup Instructions

### 1. 📋 Create Your Google Sheet
- Create a Google Sheet with the following sheets:
  - `Group 0`, `Group 1`, `Group 2`, `Group 3`, and `All`
- Copy the **Spreadsheet ID** from the URL.

### 2. 🤖 Create a Telegram Bot
- Open [@BotFather](https://t.me/BotFather) on Telegram.
- Use `/newbot` and follow the prompts.
- Copy your **Bot Token**.

### 3. 💻 Set Up Google Apps Script

- Go to [Google Apps Script](https://script.google.com)
- Create a new project and paste in the full code from `Code.gs`
- Replace the following:
  var token = "YOUR_BOT_TOKEN";
  var webAppUrl = "YOUR_WEB_APP_URL"; // leave blank for now
  var ssId = "YOUR_SPREADSHEET_ID";

### 4. 🌐 Deploy the Web App

* Go to **Deploy > Manage deployments**
* Click **+ New Deployment**
* Select **Web App**

  * Execute as: `Me`
  * Who has access: `Anyone`
* Copy the **Web App URL**
* Update the `webAppUrl` in the script with this value
* Deploy again to save changes

### 5. 🔗 Set the Webhook

* In the Apps Script editor, run the `setWebhook()` function

---

## ✅ Commands

### `/markpresent#`

Marks attendance for a group. Example:

```
/markpresent1
```

Bot will prompt for names. You can reply:

```
Jay, Rishi, Mitesh
```

These names will be marked "Present" in **Group 1** and the **All** sheet.

---

### `/summary`

Returns a summary like:

```
June 24, 2025:

Group 0: 3  
Group 1: 5  
Group 2: 2  
Group 3: 4  
——————————  
Mandal Total - 14 Balaks
```

---

### `/clear`

Clears attendance from all group sheets (Group 0–3). **Use with caution.**

---

## 🛡 Error Handling

* Any errors during execution are caught and (optionally) sent to the admin.
* Ensure valid JSON structure and check permissions on your Google Sheet if data isn't recording.

---

## 📌 Notes

* You can expand to more groups by modifying the script and updating the summary section.
* Store `.py`, `.txt`, or `.gs` backup files in version control if multiple collaborators are working on the bot.
* All timestamps are logged in the timezone set in your Google Sheet (default is EST).

---

## 🧑‍💻 Author

**Parthkumar Joshi**
Built as part of an attendance automation initiative for youth group management.

---

## 📄 License

This project is open-source under the MIT License. You are free to use, modify, and share with attribution.

```

---
