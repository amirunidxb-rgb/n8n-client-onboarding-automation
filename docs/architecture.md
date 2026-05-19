# Architecture

This document describes the architecture of the Client Onboarding Automation workflow.

━━━━━━━━━━━━━━━

## Main Workflow

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

━━━━━━━━━━━━━━━

## Error Handler Workflow

```text
Error Trigger
      ↓
Gmail - Send Failure Alert
```

━━━━━━━━━━━━━━━

## Data Flow

```text
Client submits form
      ↓
n8n receives client data
      ↓
Folder is created in Google Drive
      ↓
Trello card is created using form data
      ↓
Checklist and checklist items are added
      ↓
Welcome email is sent to the client
      ↓
Client data is saved in Google Sheets
      ↓
Admin receives internal notification
```

━━━━━━━━━━━━━━━

## Main Data Objects

### Client Form Data

```text
Client Name
Client Email
Company Name
Service Package
Start Date
Notes
```

### Google Drive Output

```text
Folder ID
Folder URL
```

### Trello Output

```text
Card ID
Card URL
Checklist ID
```

### Google Sheets Output

```text
CRM row
Invoice draft status
Onboarding status
Created timestamp
```

━━━━━━━━━━━━━━━

## External Services

```text
n8n
Google Drive
Trello
Gmail
Google Sheets
```

━━━━━━━━━━━━━━━

## Security Design

Credentials are not stored in the workflow files.

All sensitive access is handled through:

```text
n8n Credentials Manager
```

Do not commit API keys, OAuth secrets, tokens, or real client data to GitHub.
