# 🤖 IT Helpdesk Bot — Telegram + n8n

> Automated IT support ticket system built with n8n and Telegram Bot API.  
> Running in production at Grupo Heisecke / FUSQUIM (pharmaceutical industry).

---

## 📋 What it does

Employees report IT issues directly via Telegram. The bot guides them through a structured conversation, collects all necessary information and registers the ticket automatically.

**The bot captures:**
- 👤 Full name
- 📋 Issue subject & description
- 🖥️ Device IP address
- 📞 Phone number
- 📧 Email address & CC

**Then automatically:**
- ✅ Validates each field in real time
- 📊 Registers the ticket in Google Sheets
- 📧 Sends email notification to the IT team
- 💬 Sends confirmation to the user via Telegram

---

## 🏗️ Architecture

Built with a **switch-step stateful architecture** in n8n:
```
Telegram Trigger → Get State → Determine Step → Switch Step
                                                     ├── Ask Name
                                                     ├── Ask Subject
                                                     ├── Ask Description
                                                     ├── Ask IP (with validation)
                                                     ├── Ask Phone (with validation)
                                                     ├── Ask Email (with validation)
                                                     ├── Ask CC (with validation)
                                                     └── Final Confirmation → Register + Notify
```

---

## 🛠️ Stack

| Tool | Purpose |
|---|---|
| n8n | Workflow automation engine |
| Telegram Bot API | User interface |
| Google Sheets | Ticket registration |
| Email (SMTP) | IT team notifications |

---

## 📁 Files

| File | Description |
|---|---|
| `workflow.json` | n8n workflow export — import directly into your n8n instance |

---

## 🚀 How to use

1. Import `workflow.json` into your n8n instance
2. Configure your Telegram Bot token
3. Set up your Google Sheets and Email credentials in n8n
4. Activate the workflow
5. Start the bot on Telegram

---

## 👨‍💻 Author

**Mauricio González**  
IT Systems Engineer · AI Automation · Grupo Heisecke  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/gonzlezmauri)
```

