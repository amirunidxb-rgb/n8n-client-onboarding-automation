{\rtf1\ansi\ansicpg1252\cocoartf2869
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # Setup Guide\
\
This guide explains how to set up the Client Onboarding Automation workflow in n8n.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 1. Import Workflows\
\
Import these two workflow files into n8n:\
\
```text\
workflows/client-onboarding-automation.json\
workflows/client-onboarding-error-handler.json\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 2. Connect Credentials\
\
After importing, reconnect the required credentials inside n8n:\
\
```text\
Google Drive OAuth2\
Google Sheets OAuth2\
Gmail OAuth2\
Trello API Key and Token\
```\
\
Do not upload or expose real credentials on GitHub.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 3. Create Google Drive Parent Folder\
\
Create a parent folder in Google Drive:\
\
```text\
clients-n8n\
```\
\
All client folders will be created inside this folder.\
\
Example:\
\
```text\
clients-n8n/\
\uc0\u9492 \u9472 \u9472  Ali Studio - Ali Ahmadi/\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 4. Create Trello Board\
\
Create a Trello board:\
\
```text\
Client Onboarding\
```\
\
Recommended lists:\
\
```text\
New Clients\
In Progress\
Waiting for Client\
Completed\
```\
\
The workflow creates new cards inside the `New Clients` list.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 5. Create Google Sheets CRM\
\
Create a Google Sheet:\
\
```text\
Client Onboarding CRM\
```\
\
Add these headers in the first row:\
\
```text\
Client Name\
Client Email\
Company Name\
Service Package\
Start Date\
Invoice Status\
Amount\
Drive Folder Link\
Trello Card Link\
Onboarding Status\
Created At\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 6. Update Workflow Nodes\
\
After importing the workflow, check these nodes:\
\
```text\
Create folder\
Create a card\
send welcome email\
Append row in sheet\
Internal Notification\
```\
\
Make sure your credentials, folder, Trello list, Gmail account, and Google Sheet are selected correctly.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 7. Connect Error Handler\
\
Activate the error handler workflow:\
\
```text\
Client Onboarding - Error Handler\
```\
\
Then open the main workflow settings and select it as the error workflow.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
## 8. Test the Workflow\
\
Submit the test form with this sample data:\
\
```text\
Client Name: Ali Ahmadi\
Client Email: client@example.com\
Company Name: Ali Studio\
Service Package: Standard\
Start Date: 2026-05-20\
Notes: Needs website onboarding\
```\
\
Expected result:\
\
```text\
Google Drive folder created\
Trello card created\
Checklist created\
Checklist items added\
Welcome email sent\
Google Sheets row added\
Internal notification sent\
```}