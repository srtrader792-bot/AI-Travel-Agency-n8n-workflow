# AI Travel & Study-Abroad Agency Chatbot

A production-oriented n8n AI chatbot for travel and study-abroad consultancy agencies.

## Features

- AI receptionist
- Country & university information
- Spreadsheet-driven knowledge base
- Lead qualification
- Conversation memory
- Human handoff
- Appointment scheduling
- Google Sheets integration
- Staff notifications
- Bangla / Banglish / English support

## Installation

### 1. Download the workflow

Download `Claude upgrade AI Study-Abroad & Travel Agency Chatbot Workflow.json`.

### 2. Import into n8n

1. Open your self-hosted/local n8n instance.
2. Go to **Workflows**.
3. Choose **Import from File**.
4. Select the downloaded `.json` workflow.
5. Save the workflow.

### 3. Connect credentials

Connect your own credentials inside the relevant n8n nodes. Never put API keys directly into the workflow JSON.

At minimum, configure:

- OpenAI API
- Google Sheets / Google OAuth
- SMTP/email, if staff notifications are enabled

### 4. Configure the agency spreadsheets

The workflow uses Google Sheets as the editable agency data source. Configure the sheets for:

- **Country Master / University Database** — country, university, tuition, expenses, scholarships, admission requirements, visa information and other verified agency data.
- **Appointment Availability** — Date, Time, Consultant, Status, Customer Name, Customer Phone, Customer Email, Purpose and Notes.
- **Lead Database** — lead information, qualification, score, appointment and follow-up data.

Use `AVAILABLE`, `BOOKED` and `BLOCKED` for appointment status. The chatbot should only offer `AVAILABLE` slots and must verify availability again before booking.

### 5. Configure agency settings

Set the agency name and staff notification email in the workflow's configuration fields.

### 6. Test before activation

Test greeting, country/university questions, scholarships, costs, Bangla/Banglish/English conversations, human handoff, appointment availability, appointment booking, lead creation/update and staff notifications.

Only activate the workflow after the tests pass.

## Important

The spreadsheet/database should be treated as the source of truth for agency-specific education and study-abroad information. The chatbot must not invent tuition, scholarship, visa, university, embassy or financial information that is not available in the connected data source.

Never commit real customer data, API keys, OAuth tokens, passwords or other secrets to this repository.
