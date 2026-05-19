{\rtf1\ansi\ansicpg1252\cocoartf2869
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # Client Onboarding Automation\
\
Automated client onboarding workflow built with:\
\
- n8n\
- Google Drive\
- Trello\
- Gmail\
- Google Sheets\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56613  Features\
\
\'95 Collect new client details through an n8n form  \
\'95 Create a dedicated Google Drive folder for each client  \
\'95 Create a Trello onboarding card automatically  \
\'95 Add a Trello onboarding checklist  \
\'95 Add onboarding checklist items automatically  \
\'95 Send a welcome email to the client  \
\'95 Save client data in Google Sheets CRM  \
\'95 Create a simple invoice draft record  \
\'95 Send internal admin notification  \
\'95 Includes separate error handler workflow  \
\'95 Credentials removed from workflow exports  \
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u9881  Workflow Overview\
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
Error handler workflow:\
\
```text\
Error Trigger\
      \uc0\u8595 \
Gmail - Send Failure Alert\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56524  What This Automation Does\
\
When a new client submits the onboarding form, the workflow automatically:\
\
```text\
1. Receives client information\
2. Creates a Google Drive folder\
3. Creates a Trello card\
4. Adds an onboarding checklist\
5. Sends a welcome email\
6. Logs the client in Google Sheets\
7. Creates an invoice draft record\
8. Sends an internal notification\
9. Sends an error alert if the workflow fails\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55358 \u56830  Form Fields\
\
The onboarding form collects:\
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
Service package options:\
\
```text\
Basic\
Standard\
Premium\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56513  Google Drive Folder Structure\
\
For every new client, the workflow creates a folder inside the selected parent folder.\
\
Example:\
\
```text\
clients-n8n/\
      \uc0\u8595 \
Ali Studio - Ali Ahmadi/\
```\
\
Folder name format:\
\
```text\
Company Name - Client Name\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56770  Trello Setup\
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
The workflow creates each new client card inside:\
\
```text\
New Clients\
```\
\
Example card name:\
\
```text\
Ali Studio - Ali Ahmadi\
```\
\
Example card description:\
\
```text\
Client Name: Ali Ahmadi\
Email: client@example.com\
Company: Ali Studio\
Package: Standard\
Start Date: 2026-05-20\
Notes: Needs website onboarding\
\
Google Drive Folder ID:\
[Generated folder ID]\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u9989  Trello Checklist\
\
Each client card gets this checklist:\
\
```text\
Client Onboarding Checklist\
```\
\
Checklist items:\
\
```text\
Send contract\
Create invoice draft\
Schedule kickoff call\
Request brand assets\
Confirm project scope\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56551  Welcome Email\
\
The workflow sends a welcome email to the client.\
\
Example:\
\
```text\
Hi Ali Ahmadi,\
\
Welcome aboard! We're excited to start working with you.\
\
We've created your project workspace and onboarding checklist. Here are the next steps:\
\
1. Review and sign the contract\
2. Share your brand assets and project materials\
3. Confirm the project scope\
4. Schedule the kickoff call\
5. Complete the initial invoice/payment step\
\
Project folder:\
https://drive.google.com/drive/folders/[folder-id]\
\
Best regards,\
Your Team\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56516  Google Sheets CRM Structure\
\
Create a Google Sheet named:\
\
```text\
Client Onboarding CRM\
```\
\
Recommended columns:\
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
Example row:\
\
```text\
Ali Ahmadi | client@example.com | Ali Studio | Standard | 2026-05-20 | Draft | 1000 | Drive Link | Trello Link | Started | 2026-05-20\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56496  Invoice Draft Logic\
\
The workflow creates a simple invoice draft record in Google Sheets.\
\
Default package pricing:\
\
```text\
Basic    \uc0\u8594  500\
Standard \uc0\u8594  1000\
Premium  \uc0\u8594  2000\
```\
\
Default invoice status:\
\
```text\
Draft\
```\
\
Default onboarding status:\
\
```text\
Started\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56596  Internal Notification\
\
After the workflow finishes, an internal notification email is sent to the admin.\
\
Example:\
\
```text\
New client onboarding completed.\
\
Client: Ali Ahmadi\
Email: client@example.com\
Company: Ali Studio\
Package: Standard\
Start Date: 2026-05-20\
\
Google Drive Folder:\
https://drive.google.com/drive/folders/[folder-id]\
\
Trello Card:\
[trello-card-url]\
\
CRM Status:\
Added to Google Sheets\
\
Next step:\
Review onboarding checklist and follow up with the client.\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u57000  Error Handling\
\
This project includes a separate error handler workflow.\
\
If the main workflow fails, the error handler sends an email with:\
\
```text\
Workflow name\
Execution ID\
Error message\
Last executed node\
Failure time\
```\
\
Error workflow:\
\
```text\
Client Onboarding - Error Handler\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56550  Repository Structure\
\
```text\
n8n-client-onboarding-automation/\
\uc0\u9500 \u9472 \u9472  workflows/\
\uc0\u9474    \u9500 \u9472 \u9472  client-onboarding-automation.json\
\uc0\u9474    \u9492 \u9472 \u9472  client-onboarding-error-handler.json\
\uc0\u9500 \u9472 \u9472  docs/\
\uc0\u9474    \u9500 \u9472 \u9472  setup-guide.md\
\uc0\u9474    \u9492 \u9472 \u9472  architecture.md\
\uc0\u9500 \u9472 \u9472  sample-data/\
\uc0\u9474    \u9492 \u9472 \u9472  sample-client.md\
\uc0\u9500 \u9472 \u9472  templates/\
\uc0\u9474    \u9500 \u9472 \u9472  welcome-email.md\
\uc0\u9474    \u9492 \u9472 \u9472  onboarding-checklist.md\
\uc0\u9500 \u9472 \u9472  README.md\
\uc0\u9500 \u9472 \u9472  .env.example\
\uc0\u9492 \u9472 \u9472  LICENSE\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56514  Workflow Files\
\
Main workflow:\
\
```text\
workflows/client-onboarding-automation.json\
```\
\
Error handler workflow:\
\
```text\
workflows/client-onboarding-error-handler.json\
```\
\
Both workflow files are exported without credentials.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56592  Required Credentials\
\
After importing the workflows into n8n, reconnect your own credentials:\
\
```text\
Google Drive OAuth2\
Google Sheets OAuth2\
Gmail OAuth2\
Trello API Key and Token\
```\
\
Credentials are not included in this repository.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u9881  Setup Instructions\
\
1. Import the main workflow into n8n:\
\
```text\
workflows/client-onboarding-automation.json\
```\
\
2. Import the error handler workflow:\
\
```text\
workflows/client-onboarding-error-handler.json\
```\
\
3. Reconnect all required credentials.\
\
4. Create a Google Drive parent folder:\
\
```text\
clients-n8n\
```\
\
5. Create a Trello board:\
\
```text\
Client Onboarding\
```\
\
6. Create a Trello list:\
\
```text\
New Clients\
```\
\
7. Create a Google Sheet:\
\
```text\
Client Onboarding CRM\
```\
\
8. Add the required Google Sheets headers.\
\
9. Update node IDs if your Google Drive folder, Trello list, or Google Sheet is different.\
\
10. Activate the error handler workflow.\
\
11. Set the error handler workflow inside the main workflow settings.\
\
12. Activate the main workflow.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55358 \u56810  Sample Client Data\
\
Use this sample data for testing:\
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
Trello checklist created\
Checklist items added\
Welcome email sent\
Google Sheets row added\
Internal admin email sent\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55358 \u56800  Workflow Logic\
\
The workflow uses dynamic n8n expressions to pass data between nodes.\
\
Examples:\
\
```text\
Client name comes from the form submission\
Google Drive folder ID comes from the Drive node\
Trello card URL comes from the Trello card node\
Checklist ID comes from the Trello checklist node\
Google Sheets row is populated from previous workflow data\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u57056  Customization Ideas\
\
You can customize this workflow by adding:\
\
```text\
Stripe invoice creation\
PayPal invoice creation\
QuickBooks invoice creation\
Google Docs contract generation\
PDF contract export\
Slack notification\
Telegram notification\
Notion client portal\
ClickUp project creation\
Asana task creation\
Google Calendar kickoff call\
Admin approval before sending welcome email\
AI-generated onboarding summary\
Client status dashboard\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55356 \u57314  Best For\
\
This automation is useful for:\
\
```text\
Marketing agencies\
Web design agencies\
SEO agencies\
Freelancers\
Consultants\
Coaches\
Creative studios\
Small service businesses\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56508  Sellable Version\
\
This workflow can be sold as:\
\
```text\
Client Onboarding System for Agencies\
```\
\
Offer example:\
\
```text\
I build a custom client onboarding automation system that creates project folders, task boards, welcome emails, invoice draft records, and internal notifications automatically whenever a new client signs up.\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56504  Possible Service Pricing\
\
Example pricing if offered as a service:\
\
```text\
Basic Setup:    $300 - $500\
Standard Setup: $700 - $1,200\
Premium Setup:  $1,500 - $3,000+\
```\
\
Package ideas:\
\
```text\
Basic:\
Form + Google Drive + Trello\
\
Standard:\
Form + Google Drive + Trello + Gmail + Google Sheets\
\
Premium:\
Full workflow + invoice integration + contract generation + team notifications + error handling\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56592  Security Notes\
\
Do not commit sensitive data to GitHub.\
\
Never publish:\
\
```text\
Trello API tokens\
Google OAuth client secrets\
Gmail credentials\
n8n credential exports\
Real client data\
Private API keys\
Private access tokens\
Real customer emails\
```\
\
If a token is exposed:\
\
```text\
1. Revoke the token\
2. Generate a new token\
3. Update the n8n credential\
4. Check account activity\
5. Remove the exposed token from Git history\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56516  .env.example\
\
Example environment file:\
\
```env\
N8N_HOST=your-n8n-domain.com\
N8N_PROTOCOL=https\
N8N_PORT=5678\
\
GOOGLE_DRIVE_PARENT_FOLDER_ID=your_google_drive_folder_id\
GOOGLE_SHEETS_DOCUMENT_ID=your_google_sheet_id\
TRELLO_BOARD_ID=your_trello_board_id\
TRELLO_LIST_ID=your_trello_list_id\
\
ADMIN_EMAIL=your-email@example.com\
```\
\
Do not commit a real `.env` file.\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55358 \u56810  Testing Checklist\
\
Before publishing, test:\
\
```text\
[ ] Form submission works\
[ ] Google Drive folder is created\
[ ] Trello card is created\
[ ] Trello checklist is created\
[ ] All checklist items are added\
[ ] Welcome email is sent\
[ ] Google Sheets row is added\
[ ] Internal notification email is sent\
[ ] Error handler workflow is connected\
[ ] Workflow exports do not contain credentials\
[ ] Sample data does not contain real client data\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55358 \u56815  Troubleshooting\
\
Trello error:\
\
```text\
invalid value for idList\
```\
\
Solution:\
\
```text\
Use the real Trello List ID, not the list name.\
```\
\
Get Trello list IDs:\
\
```text\
https://api.trello.com/1/boards/YOUR_BOARD_ID/lists?key=YOUR_API_KEY&token=YOUR_API_TOKEN\
```\
\
Google Drive folder not created:\
\
```text\
Check Google Drive credentials\
Check parent folder ID\
Check folder permissions\
```\
\
Gmail email not sent:\
\
```text\
Check Gmail OAuth credentials\
Check recipient email\
Check Gmail permissions\
```\
\
Google Sheets row not added:\
\
```text\
Check Google Sheets credentials\
Check sheet headers\
Check selected document and sheet tab\
```\
\
Error handler not running:\
\
```text\
Make sure the error handler workflow is active\
Make sure it starts with Error Trigger\
Make sure it is selected in the main workflow settings\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56525  Roadmap\
\
Future improvements:\
\
```text\
Add Stripe invoices\
Add contract PDF generation\
Add Notion client portal\
Add Slack alerts\
Add Telegram alerts\
Add Google Calendar kickoff scheduling\
Add AI-generated client summary\
Add approval step before welcome email\
Add retry logic\
Add status dashboard\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56550  Repository\
\
```text\
https://github.com/amirunidxb-rgb/n8n-client-onboarding-automation\
```\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56424 \u8205 \u55357 \u56507  Built by Amirali Barmar\
\
\uc0\u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \u9473 \
\
\uc0\u55357 \u56516  License\
\
MIT License\
\
You are free to use, modify, and customize this project for your own business or client projects.}