# 💌 HumanMail  
[![n8n workflow](https://img.shields.io/badge/workflow-n8n-blue)](https://n8n.io)  
[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

**A Very Simple Human-in-the-Loop AI Email Automation System (IMAP + OpenAI + n8n)**  

This repository: **https://github.com/umeshyadav7988/HumanMail**  

HumanMail is an **AI-powered email workflow** built in **n8n** that automatically reads incoming emails, summarizes them using an LLM, drafts a professional reply, and sends it for **human approval** before responding — ensuring both **automation** and **human oversight**.  

---

## 🚀 Features

- 📥 **Email Trigger (IMAP)** — Automatically fetches new emails from your inbox.  
- 🧠 **AI Summarization Chain** — Uses an LLM to summarize the received email content in under 100 words.  
- ✍️ **AI Reply Generator** — Creates a concise, professional response using GPT-based models.  
- 👨‍💼 **Human-in-the-Loop Review** — Sends the generated email to a human for approval before final delivery.  
- 📤 **Automatic Reply Sending** — Once approved, the system replies to the original sender automatically.  
- 🧩 **IMAP-Compatible** — Works seamlessly with Gmail, Outlook, and other IMAP-supported providers.  

---

## ⚙️ Workflow Overview

### 1. Email Trigger (IMAP)
Listens for new emails and passes the data (sender, subject, HTML content) to the next node.

### 2. Markdown Conversion
Converts HTML email content into Markdown for better readability and processing by the AI model.

### 3. Email Summarization Chain
Summarizes the main points of the received email using a **LangChain Summarization Chain** powered by an LLM (e.g., GPT-4 or DeepSeek).

### 4. Write Email (AI Reply Generator)
Uses an AI model (`gpt-4o-mini`) to generate a **professional business email** reply — no subject, only body (under 100 words).

### 5. Human-in-the-Loop Approval
Sends the **AI-generated reply + original email content** to a human approver via email.  
The human can **approve or reject** the message.

### 6. Approval Logic
If approved, the workflow continues to send the email automatically back to the original sender.

### 7. Send Email
Sends the final, approved reply to the original sender with `Re: [Original Subject]`.

---

## 🧩 Node Summary

| Node Name | Function |
|------------|-----------|
| **Email Trigger (IMAP)** | Triggers workflow on new incoming emails |
| **Markdown** | Converts email HTML to Markdown |
| **Email Summarization Chain** | Summarizes content using LLM |
| **Write Email** | Generates AI response |
| **Set Email Text** | Stores AI output for further processing |
| **Approve Email** | Sends AI reply to human reviewer for approval |
| **Approved?** | Checks human approval |
| **Send Email** | Sends the approved reply back to the sender |
| **OpenAI / DeepSeek Chat Models** | Power the summarization and response generation |
| **Sticky Notes** | Documentation inside n8n for clarity |

---

## 🧠 Tech Stack

- **n8n** — Workflow automation engine  
- **LangChain** — LLM orchestration framework  
- **OpenAI GPT / DeepSeek Models** — Text summarization & reply generation  
- **IMAP** — Email protocol for receiving messages  
- **SMTP** — For sending automated replies  

---

## 🧩 Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/umeshyadav7988/HumanMail.git
cd HumanMail
````

### 2. Import Workflow into n8n

* Open your **n8n dashboard**
* Click **Import Workflow**
* Upload the provided `humanmail.json` workflow file

### 3. Configure Credentials

* **Email IMAP** — Connect your inbox (Gmail, Outlook, etc.)
* **Email Send (SMTP)** — Set up your sending credentials
* **OpenAI / DeepSeek API Key** — Add API keys in n8n credentials

### 4. Activate Workflow

* Turn on the workflow in n8n
* The system will now automatically handle incoming emails

---

## 🧑‍💻 Example Flow

1️⃣ New email received →
2️⃣ Summarized by LLM →
3️⃣ Draft reply generated →
4️⃣ Human reviewer approves →
5️⃣ Reply sent automatically

---

## 🔒 Human-in-the-Loop Advantage

Unlike fully automated AI responders, **HumanMail** ensures that every reply gets a **human review checkpoint** before being sent.
This keeps communication **accurate**, **context-aware**, and **safe** for business environments.



## 🧾 License

This project is licensed under the **MIT License** — feel free to use and modify it.

---

## 🌟 Author

**Umesh Rao**
💼 AI Engineer | Full Stack Developer   
🔗 [GitHub](https://github.com/umeshyadav7988)


