Automated Study Plan Generator with n8n, Google Sheets, and Twilio
📌 Overview
This project automates the creation and delivery of personalized study plans using:
Google Colab / Python for user input and data validation.
n8n workflows for AI-driven task generation, data storage, and scheduling.
Google Sheets for storing the generated study plan.
Twilio WhatsApp API for daily study reminders.
With this system, a user enters their details (subjects, exam date, available hours), and an AI model generates a day-by-day study schedule that is stored in Google Sheets and sent via WhatsApp reminders.
🚀 Features
Interactive Input: User provides subjects, exam date, available hours, and preferences via Python script.
Automated AI Task Generation: Uses OpenAI API in n8n to create daily study tasks for each subject.
Google Sheets Integration: Stores generated study plan in a structured format (date, subject, task).
Scheduled WhatsApp Reminders: Sends daily study tasks to the user automatically.
Webhook Integration: Real-time communication between Colab and n8n via webhook.
🛠️ Tech Stack
Python (Google Colab) — User input, data validation, webhook POST request.
n8n — Workflow automation & integration platform.
OpenAI GPT Models — Generates tailored study tasks.
Google Sheets API — Stores generated study plan.
Twilio WhatsApp API — Sends daily reminders.
JSON Webhooks — Connects Python input with n8n workflow.
📂 Workflow Overview
User Input (Colab)
Collects name, subjects, exam date, available daily hours, and optional preferences.
Validates date format.
Sends data to n8n webhook in JSON format.
n8n Workflow
Webhook Node: Receives data from Python.
AI Model Node: Generates day-by-day tasks.
Code Node: Formats output into date-subject-task rows.
Google Sheets Node: Appends rows to the study plan sheet.
Scheduler Node: Triggers daily reminders.
Twilio HTTP Request Node: Sends WhatsApp messages with daily tasks.
Google Sheets
Stores all generated tasks for reference and tracking.
WhatsApp Reminders
Sends automated daily study task messages until the exam date.
📦 Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/your-username/study-plan-generator.git
cd study-plan-generator
2️⃣ Set Up Python Environment
pip install -r requirements.txt
3️⃣ Set Up n8n Workflow
Deploy n8n locally or on cloud.
Create a new workflow with:
Webhook Node
OpenAI GPT Node
Code Node
Google Sheets integration
Scheduler
Twilio HTTP Request Node
Replace API keys & credentials in respective nodes.
4️⃣ Configure Google Sheets
Create a Google Sheet with columns:
date | subject | task
Connect to n8n Google Sheets node.
5️⃣ Configure Twilio WhatsApp API
Set up Twilio Sandbox for WhatsApp.
Replace API credentials in HTTP Request node.
▶️ Usage
Run the n8n.ipynb notebook in Google Colab or locally.
Enter your details:
Name: John Doe
Subjects: Math, Physics, Chemistry
Exam Date: 2025-09-01
Daily Hours: 4
Preferences: Focus on weak areas
The script sends data to the n8n webhook.
n8n generates a study plan and stores it in Google Sheets.
Daily reminders are sent via WhatsApp.
📊 Example Output
Google Sheets:
date	subject	task
2025-08-01	Math	Review key topics and create a summary.
2025-08-02	Physics	Solve practice problems and past papers.
WhatsApp Reminder:
Hi John Doe! 📚
Your task for today (2025-08-02):
Subject: Physics
Task: Solve practice problems and past papers.
📅 Future Enhancements
Add progress tracking with percentage completion.
Integrate multiple reminder channels (Email, Telegram).
Support multi-user plans in a shared Google Sheet.
Add AI revision strategy based on performance feedback.
📜 License
This project is licensed under the MIT License.
