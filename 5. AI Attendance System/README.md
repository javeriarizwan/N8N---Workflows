
# AI Attendance Tracking System

Automated attendance workflow built in n8n that captures Slack messages, detects check-in or check-out intent with AI, records attendance in Google Sheets, handles monthly sheet creation automatically, and sends confirmation back to employees in Slack.

## What it does

* Listens to attendance messages in Slack
* Detects check-in or check-out using AI
* Extracts date and time from user messages
* Handles late-night and midnight shift cases
* Creates monthly attendance sheets automatically
* Updates existing attendance records in Google Sheets
* Sends instant Slack confirmation to the employee

## Tools used

* n8n
* OpenAI
* Slack
* Google Sheets
* JavaScript nodes

## Use cases

* Employee attendance tracking
* Slack-based check-in/check-out
* Shift logging
* Monthly attendance record automation

## Outcome

This workflow removes manual attendance entry, reduces HR/admin work, and creates a clean, automated attendance system directly through Slack.

