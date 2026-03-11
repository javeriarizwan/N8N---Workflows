# AI Interview Reminder and Response Automation System

Built an end-to-end interview automation workflow in n8n that sends WhatsApp interview reminders, listens to candidate replies, and automatically handles confirmation, cancellation, and rescheduling.

## What it does

* Pulls interview events from Google Calendar every 15 minutes
* Detects valid interview events and candidate phone numbers
* Sends 1-hour and 4-hour WhatsApp reminders automatically
* Prevents duplicate reminders using Postgres logging
* Stores reminder activity in Google Sheets
* Receives candidate replies through webhook
* Uses AI to classify replies into confirm, cancel, reschedule, or unknown
* Sends confirmation messages automatically
* Cancels interviews in Google Calendar when candidate declines
* Reschedules interviews by generating available slots and updating calendar + sheet
* Handles unclear replies by asking the candidate to reply with CONFIRM, CANCEL, or RESCHEDULE

## Tools used

* n8n
* OpenAI
* WhatsApp Cloud API
* Google Calendar
* Google Sheets
* Postgres
* JavaScript code nodes
* Webhooks

## Use cases

* HR interview scheduling automation
* Candidate reminder and follow-up system
* WhatsApp-based interview management
* Reschedule and cancellation handling
* Calendar and sheet synchronization

## Outcome

This workflow reduces manual HR coordination by automating interview reminders and candidate communication, while keeping Google Calendar, WhatsApp, Postgres, and Google Sheets fully in sync.


