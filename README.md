# N8N Workflow Portfolio

This repository contains a collection of N8N workflows designed to automate various business processes. Each workflow leverages the power of automation, AI, and integrations to solve specific challenges.

---

## 1. WhatsApp Lead Qualification Bot
An AI-assisted chatbot for **UK Commercial Flooring** that collects structured quote request details via WhatsApp and stores them in Google Sheets. It uses OpenAI for intent extraction and ensures seamless user interaction.

### Features:
- Collects project details, contact information, and preferences.
- Routes messages through interactive or AI-driven paths.
- Stores structured data in Google Sheets.

### Tech Stack:
- **n8n**
- **OpenAI API**
- **Google Sheets API**
- **WhatsApp Cloud API**

---

## 2. Automated AI Real Estate News Briefing System
A daily investor newsletter pipeline for a US real estate company. It automates research, formatting, and email delivery using AI and Google Sheets.

### Features:
- Researches market updates like mortgage rates and housing inventory.
- Formats insights into branded HTML emails.
- Sends newsletters automatically via Gmail.

### Tech Stack:
- **n8n**
- **Google Sheets API**
- **Perplexity AI API**
- **Gmail API**
- **JavaScript for data transformation**

---

## 3. AI-Powered Data Source Discovery Workflow
An intelligent system that identifies the most relevant data source based on user requests. It routes tasks to specialized research agents and exports results as CSV files.

### Features:
- Detects user intent and extracts key parameters.
- Routes requests to appropriate research tools.
- Saves results in Google Sheets and exports CSVs.

### Tech Stack:
- **n8n**
- **OpenAI API**
- **Google Sheets API**
- **Custom JavaScript nodes**

---

## 4. AI HR Event Reminder Workflow
An automated HR reminder system that generates and sends event-specific messages to employees and clients via Slack.

### Features:
- Reads upcoming events from Google Sheets.
- Sends reminders with AI-generated messages.
- Updates event statuses to prevent duplicates.

### Tech Stack:
- **n8n**
- **OpenAI API**
- **Google Sheets API**
- **Slack API**
- **Webhooks**

---

## 5. AI Attendance Tracking System
A Slack-integrated attendance system that automates check-ins and check-outs, records data in Google Sheets, and handles shift-specific cases.

### Features:
- Detects attendance intent using AI.
- Creates monthly attendance sheets automatically.
- Sends instant Slack confirmations.

### Tech Stack:
- **n8n**
- **OpenAI API**
- **Slack API**
- **Google Sheets API**
- **JavaScript nodes**

---

## 6. AI Interview Reminder and Response Automation System
An end-to-end interview management workflow that automates reminders, handles candidate replies, and synchronizes data across Google Calendar, WhatsApp, and Google Sheets.

### Features:
- Sends WhatsApp reminders for interviews.
- Classifies candidate replies (confirm, cancel, reschedule).
- Updates Google Calendar and logs activity in Google Sheets.

### Tech Stack:
- **n8n**
- **OpenAI API**
- **WhatsApp Cloud API**
- **Google Calendar API**
- **Google Sheets API**
- **Postgres**
- **Webhooks**

---

## 7. AI Appointment Booking Assistant
A streamlined appointment scheduling workflow that validates requests, checks availability, books slots, and confirms appointments via AI voice calls.

### Features:
- Collects customer details through a webhook.
- Validates and books appointments using Google Calendar.
- Saves lead data in Airtable and triggers voice confirmation calls.

### Tech Stack:
- **n8n**
- **OpenAI API**
- **Google Calendar API**
- **Airtable API**
- **Vapi AI Voice API**
- **Webhooks**

---

This portfolio showcases the versatility of N8N in automating complex workflows across various industries. Each workflow is tailored to specific use cases, ensuring efficiency and scalability.