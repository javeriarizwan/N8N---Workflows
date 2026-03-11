# Automated AI Real Estate News Briefing System

## Overview

I built an automated news briefing workflow in **n8n** for a US real estate data company. The system collects daily content themes from Google Sheets, uses AI to research investor-relevant market updates, formats the results into a branded HTML newsletter, and sends it automatically through Gmail.

This workflow turns raw market signals into a polished, investor-friendly email without requiring manual writing every day.

---

## Problem

Real estate investors and wholesalers need fast, relevant updates on things like:

* mortgage rates
* housing inventory
* price cuts
* foreclosure and distress signals
* landlord and compliance changes
* tactical market insights

Manually researching, writing, formatting, and sending a daily email takes time and creates inconsistency. The client needed an automated system that could deliver high-quality briefings every day with minimal manual effort.

---

## Solution

I created a fully automated **daily investor newsletter pipeline** using **n8n**, **Google Sheets**, **Perplexity AI**, custom **JavaScript transformation logic**, and **Gmail**.

The workflow:

1. Runs on a schedule automatically
2. Pulls the content theme and audience for the day from Google Sheets
3. Sends a structured research prompt to Perplexity
4. Receives fresh investor-relevant news and source-backed insights
5. Converts the output into a branded HTML email
6. Sends the final email automatically through Gmail

---

## Tools & Stack

* **n8n**
* **Google Sheets**
* **Perplexity API**
* **JavaScript in n8n Code nodes**
* **Gmail API**
* **HTML email templating**

---

## Workflow Architecture

### 1. Schedule Trigger

The workflow starts automatically on a scheduled interval, allowing the newsletter to be generated daily without manual action.

### 2. Google Sheets Lookup

The system reads a spreadsheet containing:

* day-based content themes
* target audience
* subject hooks
* promotional blocks
* CTA copy

This makes the workflow flexible because content direction can be changed without editing the automation.

### 3. Day Matching Logic

A JavaScript node matches the current day with the correct spreadsheet row so the workflow always uses the right theme and messaging for that day.

### 4. AI Research Layer

The selected row is passed into a Perplexity prompt designed to fetch:

* real estate market news
* investor-relevant economic updates
* distress trends
* housing signals
* compliance and regulatory changes
* tactical operator insights

The AI is instructed to focus on the last 24–48 hours and provide newsletter-friendly output with source-backed information.

### 5. HTML Newsletter Builder

A custom JavaScript node transforms the model output into a polished branded newsletter. This includes:

* subject line generation
* “What matters today” intro
* news cards with summaries
* call-to-action section
* promotional block for the company
* social links
* professional email signature
* footer and compliance links

### 6. Email Delivery

The final HTML email is sent automatically via Gmail to the target recipient.

---

## Key Features

* Fully automated daily execution
* Dynamic theme selection from spreadsheet
* AI-generated investor-focused content
* Source-aware output
* Branded HTML email generation
* Reusable and easy to scale
* Low-maintenance content operations workflow

---

## Business Value

This automation helps the business:

* save hours of manual research and formatting
* maintain daily consistency in outbound investor communication
* publish timely market updates faster
* improve email quality with structured branded output
* scale content production without adding staff time

---

## My Role

I handled the workflow design end-to-end, including:

* automation planning
* node architecture
* spreadsheet-driven logic
* AI prompt engineering
* JavaScript transformation
* branded email template generation
* Gmail delivery setup

---
