# SmartLead Pro ⚡ — AI-Powered Lead Scoring & Automation System

SmartLead Pro is an intelligent lead management tool designed to streamline your sales funnel. It automatically captures leads, analyzes their buying intent using AI, classifies their urgency, and stores structured data in Airtable — all through a low-code automation stack built with **n8n**.

> **Use Case:** Ideal for startups, freelancers, or growing sales teams looking to automate lead intake, scoring, and prioritization without complex infrastructure.

---

## 🚀 Features

- ✅ Real-time lead capture via webhook
- 🧠 AI-powered lead scoring (1–10) using Cohere
- ⚡ Urgency and intent classification
- 📊 Seamless Airtable integration to store structured lead data
- 🔔 (Optional) Slack, Gmail, Telegram alerts
- ✍️ (Optional) Smart auto-reply generation
- 🔧 Fully extendable and no-code friendly

---

## 🔁 Workflow Overview

graph TD

    A[Lead Form / Webhook] --> B[n8n Webhook Node]
    B --> C[Prompt Builder Node]
    C --> D[Cohere Classifier (AI Scoring)]
    D --> E[Score Extractor]
    B --> E
    E --> F[Merge Node]
    F --> G[Airtable Output]
    G --> H[Optional: Notification or Smart Reply Node]

📦 Tech Stack
n8n – Open-source workflow automation

Cohere API – Language model for lead scoring and classification

Airtable – Lightweight CRM / data storage

cURL – For manual lead testing and simulation

(Optional) Gmail, Slack, Telegram for notifications


Example of how to execute after opening n8n in your local host from your terminal:

curl -X POST http://localhost:5678/webhook/smartlead-pro \
  -H "Content-Type: application/json" \
  -d '{
    "Name": "Teja Rao",
    "Email": "teja@example.com",
    "Message": "We’re looking for an AI-based solution to streamline our recruitment process. Can you assist?"
  }'

PS: Have all your Airtable database entries ready, activate the workflow in n8n, execute, and give the command in your terminal. 

There you have it. Hope you had as much fun as I had in building it.

Magic is real.
