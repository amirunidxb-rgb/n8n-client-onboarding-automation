# Client Onboarding Automation

Automated client onboarding workflow built with:

- n8n
- Google Drive
- Trello
- Gmail
- Google Sheets

━━━━━━━━━━━━━━━

## Features

- Collect new client details through an n8n form
- Create a dedicated Google Drive folder for each client
- Create a Trello onboarding card automatically
- Add a Trello onboarding checklist
- Add onboarding checklist items automatically
- Send a welcome email to the client
- Save client data in Google Sheets CRM
- Create a simple invoice draft record
- Send internal admin notification
- Includes separate error handler workflow
- Credentials removed from workflow exports

━━━━━━━━━━━━━━━

## Workflow Overview

```text
Form Trigger
      ↓
Google Drive - Create Client Folder
      ↓
Trello - Create Client Card
      ↓
Trello - Create Checklist
      ↓
Trello - Add Checklist Items
      ↓
Gmail - Send Welcome Email
      ↓
Google Sheets - Add CRM / Invoice Draft Row
      ↓
Gmail - Send Internal Notification
```

Error handler workflow:

```text
Error Trigger
      ↓
Gmail - Send Failure Alert
```

━━━━━━━━━━━━━━━

## What This Automation Does

When a new client submits the onboarding form, the workflow automatically:

```text
1. Receives client information
2. Creates a Google Drive folder
3. Creates a Trello card
4. Adds an onboarding checklist
5. Sends a welcome email
6. Logs the client in Google Sheets
7. Creates an invoice draft record
8. Sends an internal notification
9. Sends an error alert if the workflow fails
```

━━━━━━━━━━━━━━━

## Form Fields

The onboarding form collects:

```text
Client Name
Client Email
Company Name
Service Package
Start Date
Notes
```

Service package options:

```text
Basic
Standard
Premium
```

━━━━━━━━━━━━━━━

## Google Drive Folder Structure

For every new client, the workflow creates a folder inside the selected parent folder.

Example:

```text
clients-n8n/
      ↓
Ali Studio - Ali Ahmadi/
```

Folder name format:

```text
Company Name - Client Name
```

━━━━━━━━━━━━━━━

## Trello Setup

Create a Trello board:

```text
Client Onboarding
```

Recommended lists:

```text
New Clients
In Progress
Waiting for Client
Completed
```

The workflow creates each new client card inside:

```text
New Clients
```

Example card name:

```text
Ali Studio - Ali Ahmadi
```

━━━━━━━━━━━━━━━

## Trello Checklist

Each client card gets this checklist:

```text
Client Onboarding Checklist
```

Checklist items:

```text
Send contract
Create invoice draft
Schedule kickoff call
Request brand assets
Confirm project scope
```

━━━━━━━━━━━━━━━

## Welcome Email

The workflow sends a welcome email to the client.

Example:

```text
Hi Ali Ahmadi,

Welcome aboard! We're excited to start working with you.

We've created your project workspace and onboarding checklist. Here are the next steps:

1. Review and sign the contract
2. Share your brand assets and project materials
3. Confirm the project scope
4. Schedule the kickoff call
5. Complete the initial invoice/payment step

Project folder:
https://drive.google.com/drive/folders/[folder-id]

Best regards,
Your Team
```

━━━━━━━━━━━━━━━

## Google Sheets CRM Structure

Create a Google Sheet named:

```text
Client Onboarding CRM
```

Recommended columns:

```text
Client Name
Client Email
Company Name
Service Package
Start Date
Invoice Status
Amount
Drive Folder Link
Trello Card Link
Onboarding Status
Created At
```

Example row:

```text
Ali Ahmadi | client@example.com | Ali Studio | Standard | 2026-05-20 | Draft | 1000 | Drive Link | Trello Link | Started | Created At
```

━━━━━━━━━━━━━━━

## Invoice Draft Logic

The workflow creates a simple invoice draft record in Google Sheets.

Default package pricing:

```text
Basic    → 500
Standard → 1000
Premium  → 2000
```

Default invoice status:

```text
Draft
```

Default onboarding status:

```text
Started
```

━━━━━━━━━━━━━━━

## Internal Notification

After the workflow finishes, an internal notification email is sent to the admin.

━━━━━━━━━━━━━━━

## Error Handling

This project includes a separate error handler workflow.

If the main workflow fails, the error handler sends an email with:

```text
Workflow name
Execution ID
Error message
Last executed node
Failure time
```

━━━━━━━━━━━━━━━

## Repository Structure

```text
n8n-client-onboarding-automation/
├── workflows/
│   ├── client-onboarding-automation.json
│   └── client-onboarding-error-handler.json
├── docs/
│   ├── setup-guide.md
│   └── architecture.md
├── sample-data/
│   └── sample-client.md
├── templates/
│   ├── welcome-email.md
│   └── onboarding-checklist.md
├── README.md
└── LICENSE
```

━━━━━━━━━━━━━━━

## Workflow Files

Main workflow:

```text
workflows/client-onboarding-automation.json
```

Error handler workflow:

```text
workflows/client-onboarding-error-handler.json
```

Both workflow files are exported without credentials.

━━━━━━━━━━━━━━━

## Required Credentials

After importing the workflows into n8n, reconnect your own credentials:

```text
Google Drive OAuth2
Google Sheets OAuth2
Gmail OAuth2
Trello API Key and Token
```

Credentials are not included in this repository.

━━━━━━━━━━━━━━━

## Setup Instructions

1. Import the main workflow into n8n:

```text
workflows/client-onboarding-automation.json
```

2. Import the error handler workflow:

```text
workflows/client-onboarding-error-handler.json
```

3. Reconnect all required credentials.
4. Create a Google Drive parent folder.
5. Create a Trello board and list.
6. Create a Google Sheet CRM.
7. Update node IDs if your Google Drive folder, Trello list, or Google Sheet is different.
8. Activate the error handler workflow.
9. Set the error handler workflow inside the main workflow settings.
10. Activate the main workflow.

━━━━━━━━━━━━━━━

## Sample Client Data

```text
Client Name: Ali Ahmadi
Client Email: client@example.com
Company Name: Ali Studio
Service Package: Standard
Start Date: 2026-05-20
Notes: Needs website onboarding
```

Expected result:

```text
Google Drive folder created
Trello card created
Trello checklist created
Checklist items added
Welcome email sent
Google Sheets row added
Internal admin email sent
```

━━━━━━━━━━━━━━━

## Best For

This automation is useful for:

```text
Marketing agencies
Web design agencies
SEO agencies
Freelancers
Consultants
Coaches
Creative studios
Small service businesses
```

━━━━━━━━━━━━━━━

## Sellable Version

This workflow can be sold as:

```text
Client Onboarding System for Agencies
```

Offer example:

```text
I build a custom client onboarding automation system that creates project folders, task boards, welcome emails, invoice draft records, and internal notifications automatically whenever a new client signs up.
```

━━━━━━━━━━━━━━━

## Security Notes

Do not commit sensitive data to GitHub.

Never publish:

```text
Trello API tokens
Google OAuth client secrets
Gmail credentials
n8n credential exports
Real client data
Private API keys
Private access tokens
Real customer emails
```

If a token is exposed:

```text
1. Revoke the token
2. Generate a new token
3. Update the n8n credential
4. Check account activity
5. Remove the exposed token from Git history
```

━━━━━━━━━━━━━━━

## Troubleshooting

Trello error:

```text
invalid value for idList
```

Solution:

```text
Use the real Trello List ID, not the list name.
```

Get Trello list IDs:

```text
https://api.trello.com/1/boards/YOUR_BOARD_ID/lists?key=YOUR_API_KEY&token=YOUR_API_TOKEN
```

━━━━━━━━━━━━━━━

## Roadmap

Future improvements:

```text
Add Stripe invoices
Add contract PDF generation
Add Notion client portal
Add Slack alerts
Add Telegram alerts
Add Google Calendar kickoff scheduling
Add AI-generated client summary
Add approval step before welcome email
Add retry logic
Add status dashboard
```

━━━━━━━━━━━━━━━

## Repository

```text
https://github.com/amirunidxb-rgb/n8n-client-onboarding-automation
```

━━━━━━━━━━━━━━━

## Built By

Amirali Barmar

━━━━━━━━━━━━━━━

## License

MIT License
