{\rtf1\ansi\ansicpg1252\cocoartf2869
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # Architecture\
\
This document describes the architecture of the Client Onboarding Automation workflow.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## Main Workflow\
\
```text\
Form Trigger\
      \uc0\u8595 \
Google Drive - Create Client Folder\
      \uc0\u8595 \
Trello - Create Client Card\
      \uc0\u8595 \
Trello - Create Checklist\
      \uc0\u8595 \
Trello - Add Checklist Items\
      \uc0\u8595 \
Gmail - Send Welcome Email\
      \uc0\u8595 \
Google Sheets - Add CRM / Invoice Draft Row\
      \uc0\u8595 \
Gmail - Send Internal Notification\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## Error Handler Workflow\
\
```text\
Error Trigger\
      \uc0\u8595 \
Gmail - Send Failure Alert\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## Data Flow\
\
```text\
Client submits form\
      \uc0\u8595 \
n8n receives client data\
      \uc0\u8595 \
Folder is created in Google Drive\
      \uc0\u8595 \
Trello card is created using form data\
      \uc0\u8595 \
Checklist and checklist items are added\
      \uc0\u8595 \
Welcome email is sent to the client\
      \uc0\u8595 \
Client data is saved in Google Sheets\
      \uc0\u8595 \
Admin receives internal notification\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## Main Data Objects\
\
### Client Form Data\
\
```text\
Client Name\
Client Email\
Company Name\
Service Package\
Start Date\
Notes\
```\
\
### Google Drive Output\
\
```text\
Folder ID\
Folder URL\
```\
\
### Trello Output\
\
```text\
Card ID\
Card URL\
Checklist ID\
```\
\
### Google Sheets Output\
\
```text\
CRM row\
Invoice draft status\
Onboarding status\
Created timestamp\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## External Services\
\
```text\
n8n\
Google Drive\
Trello\
Gmail\
Google Sheets\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## Security Design\
\
Credentials are not stored in the workflow files.\
\
All sensitive access is handled through:\
\
```text\
n8n Credentials Manager\
```\
\
Do not commit API keys, OAuth secrets, tokens, or real client data to GitHub.}