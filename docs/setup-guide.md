# Setup Guide

This guide explains how to set up the Client Onboarding Automation workflow in n8n.

━━━━━━━━━━━━━━━

## 1. Import Workflows

Import these two workflow files into n8n:

```text
workflows/client-onboarding-automation.json
workflows/client-onboarding-error-handler.json
```

━━━━━━━━━━━━━━━

## 2. Connect Credentials

After importing, reconnect the required credentials inside n8n:

```text
Google Drive OAuth2
Google Sheets OAuth2
Gmail OAuth2
Trello API Key and Token
```

Do not upload or expose real credentials on GitHub.

━━━━━━━━━━━━━━━

## 3. Create Google Drive Parent Folder

Create a parent folder in Google Drive:

```text
clients-n8n
```

All client folders will be created inside this folder.

Example:

```text
clients-n8n/
└── Ali Studio - Ali Ahmadi/
```

━━━━━━━━━━━━━━━

## 4. Create Trello Board

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

The workflow creates new cards inside the `New Clients` list.

━━━━━━━━━━━━━━━

## 5. Create Google Sheets CRM

Create a Google Sheet:

```text
Client Onboarding CRM
```

Add these headers in the first row:

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

━━━━━━━━━━━━━━━

## 6. Update Workflow Nodes

After importing the workflow, check these nodes:

```text
Create folder
Create a card
send welcome email
Append row in sheet
Internal Notification
```

Make sure your credentials, folder, Trello list, Gmail account, and Google Sheet are selected correctly.

━━━━━━━━━━━━━━━

## 7. Connect Error Handler

Activate the error handler workflow:

```text
Client Onboarding - Error Handler
```

Then open the main workflow settings and select it as the error workflow.

━━━━━━━━━━━━━━━

## 8. Test the Workflow

Submit the test form with this sample data:

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
Checklist created
Checklist items added
Welcome email sent
Google Sheets row added
Internal notification sent
```
