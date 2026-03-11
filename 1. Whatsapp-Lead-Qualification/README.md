# WhatsApp Lead Qualification Bot — n8n Workflow

This workflow powers an AI-assisted WhatsApp chatbot for **UK Commercial Flooring**. It collects quote request details from users in a structured way, stores them in **Google Sheets**, and sends a formatted summary for final review and submission.

## What this workflow does

The bot talks to users on WhatsApp and captures:

* Project location
* Project details / current surface
* Full name
* Email address
* Phone number
* Company name
* Preferred contact method

It uses an OpenAI-powered intent extraction step to understand free-text replies and route the user to the correct next step.

---

## Main components

### 1. WhatsApp Trigger

Starts the workflow whenever a new WhatsApp message is received.

### 2. Interactive vs Text Detection

Checks whether the incoming message is:

* an interactive reply (button/list)
* a normal text message

This decides whether the workflow should go through the interactive router or the AI intent detection path.

### 3. OpenAI Intent Detection Agent

Extracts structured intent from user text replies.

Examples:

* greeting
* location
* project_details
* project_details_other
* full_name
* email
* phone
* company
* preferred_contact
* skip
* other

It also calls the **Get Data** tool first to fetch the user’s current row from Google Sheets and determine which step is expected next.

### 4. Google Sheets

Used as the workflow state store.

Each user is tracked by **Phone** as the matching key.
The sheet keeps the current progress for each lead.

### 5. Interactive Router

Handles WhatsApp list replies and button replies such as:

* flooring selection
* project size
* preferred contact method
* final confirmation

### 6. Formatting + Submission

Once all fields are collected, the workflow:

* fetches submitted data from Google Sheets
* formats it into a WhatsApp-friendly summary
* asks the user to confirm
* sends an email summary

---

## Flow overview

### Step 1: User starts conversation

The workflow receives a message from WhatsApp.

### Step 2: Message type is checked

* **Interactive message** → routed through interactive flow
* **Text message** → routed through AI extraction flow

### Step 3: User state is checked from Google Sheets

The workflow fetches the row for the phone number to determine whether the user is:

* a new lead
* an existing lead continuing a previous step

### Step 4: Expected field is detected

The AI agent determines which field should be collected next based on what is already filled in the sheet.

### Step 5: Data is validated and stored

The extracted value is written into Google Sheets using **appendOrUpdate**.

### Step 6: User is asked the next question

The next WhatsApp message is sent based on the updated workflow state.

### Step 7: Final review

Once all required fields are collected:

* the full summary is formatted
* the user is asked to confirm submission
* a confirmation message is sent
* an email summary is generated

---

## Data captured in Google Sheets

Recommended columns:

* Phone
* Flooring
* Location
* Project Size
* Project Details
* Project Details Other
* Full Name
* Email Address
* Phone_Number
* Company
* Preferred Contact

The workflow uses **Phone** as the matching column for updates.

---

## Key workflow behaviors

### Greeting handling

If the user sends a simple greeting like:

* hi
* hello
* hey
* salam

The bot responds with a welcome message and begins the quote flow.

### Skip handling

If the user sends `skip` or `.`, the workflow marks that step as skipped where applicable.

### Project details handling

For current surface selection, users can reply with comma-separated numeric options like:

* `1`
* `1,3`
* `2,4`

These are mapped to readable values such as:

* Concrete
* Existing Coating/Resin
* Tiles
* Timber

If the user says `other` or `5`, they are prompted to describe it manually.

### Email validation

The workflow checks whether the submitted email looks valid before moving on.

### Phone validation

Phone input is checked for minimum digit length.

### Final confirmation

Before final submission, the user receives a WhatsApp summary of all captured information and confirms it.

---

## Nodes used

This workflow mainly uses:

* **WhatsApp Trigger**
* **If**
* **Switch**
* **HTTP Request**
* **OpenAI Chat Model**
* **AI Agent**
* **Google Sheets**
* **Google Sheets Tool**
* **Code**
* **Gmail**
* **WhatsApp Send**

---

## External services required

To run this workflow, you need:

### WhatsApp Cloud API

Used for:

* receiving incoming messages
* sending text messages
* sending interactive buttons and lists

### OpenAI

Used for:

* intent detection
* step-aware extraction from user text

### Google Sheets

Used for:

* persistent lead tracking
* field-by-field updates
* submission summary lookup

### Gmail

Used for:

* sending a final quote summary email

---

## Required setup

Before using this workflow, replace all placeholders like:

* `Your Whatsapp Phone Number ID`
* `Your Auth Token`
* `your id`

With your real values.

You also need to configure credentials in n8n for:

* WhatsApp
* OpenAI
* Google Sheets
* Gmail

---

## Important notes

### 1. Your pasted JSON had duplicate full workflow objects

Only one root JSON object should exist in the final import file.

### 2. Trailing commas break JSON

Examples that break import:

```json
{
  "name": "Test",
}
```

Correct version:

```json
{
  "name": "Test"
}
```

### 3. Some placeholders are still dummy values

Importing valid JSON is different from running a valid workflow.
You still need to connect real credentials and IDs.

---

## Expected use case

This workflow is useful for businesses that want to:

* qualify WhatsApp leads automatically
* collect quote details in sequence
* avoid manual back-and-forth
* keep all leads organized in Google Sheets
* send structured summaries internally

---

## Example conversation path

1. User says hello
2. Bot welcomes them
3. Bot asks for confirmation to continue
4. User selects flooring type
5. Bot asks for project location
6. Bot asks for project size
7. Bot asks for current surface details
8. Bot asks for full name
9. Bot asks for email
10. Bot asks for phone number
11. Bot asks for company
12. Bot asks for preferred contact method
13. Bot sends final summary
14. User confirms
15. Bot marks submission complete and sends email summary

---

## Troubleshooting

### Workflow does not import

Check for:

* duplicate JSON objects in one file
* trailing commas
* broken quotes
* missing braces or brackets

### WhatsApp messages fail

Check:

* phone number ID
* access token
* correct Graph API endpoint
* WhatsApp Cloud API permissions

### Google Sheets updates fail

Check:

* correct spreadsheet ID
* correct sheet tab
* matching column exists
* credentials are connected

### AI extraction behaves incorrectly

Check:

* prompt instructions
* step logic in sheet
* output parser formatting
* expected field routing in `Router 1`

---

