📧 Gmail Automation using n8n
This project automates the process of sending personalized emails using n8n with data sourced from Google Sheets. It was built as part of an internship task to demonstrate low-code workflow automation integrated with external services like Gmail, Google Sheets, and Telegram.

🚀 Features
📤 Automatically sends emails to users listed in a Google Sheet (Sheet 1).

📄 Dynamically fetches subject and body templates from a separate Google Sheet (Sheet 2).

🔁 Loops through each user and sends customized emails using the Gmail node.

🧠 Implements basic Model Context Protocol (MCP) manually using the Edit Fields node to store:

Recipient name and email

Email subject and body

Timestamp of when the email was sent

Email status (sent/failed)

Source and channel metadata

📊 Logs the email status and MCP metadata into a separate Google Sheet for auditing.

🔒 Designed with scalability and future AI integration (e.g., Gemini) in mind.

🛠️ Tools & Technologies
n8n

Google Sheets

Gmail API (via n8n Gmail Node)

Telegram Bot (optional extension)

Manual MCP (Model Context Protocol) structure via Edit Fields

📂 Project Structure
pgsql
Copy
Edit
📁 n8n-workflow
├── Google Sheet 1 → Leads (Name, Email)
├── Google Sheet 2 → Email Templates (Subject, Body)
├── n8n Nodes: Webhook → Sheets → Loop → Merge → Gmail → Log Status
└── Manual MCP: Added inside Edit Fields node (Status, Timestamp, Metadata)
🧩 Example MCP Fields Used
Field Name	Description
recipient_name	Name from Sheet 1
recipient_email	Email from Sheet 1
template_subject	Subject from Sheet 2
template_body	Body from Sheet 2
sent_at	Timestamp when email was processed
status	Email delivery status: Sent or Failed
channel	Target platform (e.g., Gmail)
created_by	Source system (e.g., Google Sheets)

✅ Status
✅ Successfully implemented and tested for dynamic email delivery with audit logging.
📈 Ready for future improvements like:

Gemini integration for smart template selection

Conditional branching based on urgency/context

Multi-channel support (Telegram, SMS, etc.)
