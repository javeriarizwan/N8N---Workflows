
# AI HR Event Reminder Workflow

Automated HR reminder system built in n8n that checks upcoming events from Google Sheets, uses AI to generate team and client-ready messages, sends reminders to employees on Slack, and updates event status automatically.

## What it does

* Runs on a daily schedule
* Reads upcoming events from Google Sheets
* Picks the next valid event within the next 14 days
* Generates event-specific team and client messages with AI
* Sends reminders to employees on Slack
* Uses Slack buttons for optional client-message approval
* Updates the sheet status to avoid duplicate reminders

## Tools used

* n8n
* OpenAI
* Google Sheets
* Slack
* Webhooks
* JavaScript nodes

## Use cases

* Public holiday reminders
* Internal event announcements
* Office closure communication
* HR notification automation

## Outcome

This workflow reduces manual HR effort, keeps reminders consistent, and automates both employee and client communication around company events.

