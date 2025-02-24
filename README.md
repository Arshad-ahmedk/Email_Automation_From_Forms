# Email_Automation_From_Forms
This repository contains a Google Apps Script that automates the process of sending personalized emails to participants who register for an event.
## Features
- Automatically sends personalized emails upon form submission.
- Updates the "Mail Status" column in the Google Sheet.
- Provides event details, coordinator contacts, and social media links in the email.
- Includes an "Add to Calendar" feature for easy scheduling.

## Prerequisites
1. A Google Account.
2. A Google Form linked to a Google Sheet where responses are stored.
3. Google Apps Script editor access.

## Setup Guide

### Step 1: Set Up Google Form & Sheet
- Create a Google Form with fields for "Name" and "Email Address".
- Link the form responses to a Google Sheet.
- Ensure a column named "Mail Status" exists or will be created automatically.

### Step 2: Add the Google Apps Script
1. Open the Google Sheet.
2. Click on `Extensions` > `Apps Script`.
3. Delete any existing code and paste the provided script.
4. Save the script.

### Step 3: Enable Trigger
1. In the Apps Script editor, go to `Triggers` (`clock` icon).
2. Click `+ Add Trigger`.
3. Set up the trigger as follows:
   - **Choose function to run**: `onFormSubmit`
   - **Choose deployment**: `Head`
   - **Select event source**: `From form`
   - **Select event type**: `On form submit`
4. Save the trigger.

### Step 4: Authorize and Deploy
- Click `Run` to authorize the script.
- Grant necessary permissions.
- Test by submitting a form response.

## How It Works
1. When a form is submitted, `onFormSubmit(e)` is triggered.
2. The script retrieves form responses and checks for an email address.
3. A personalized email is sent using GmailApp.
4. The "Mail Status" column in the sheet is updated to "Email Sent".

## Example Email Format
- Subject: `Thank You for Registering, {name}!`
- Includes event details, coordinator contacts, and a calendar invite link.

## Troubleshooting
- If emails are not sent, check script execution logs (`View > Logs`).
- Ensure the email column in the sheet is named correctly.
- If necessary, manually create the "Mail Status" column.

## Contributions
Feel free to fork this repository and enhance the script as needed!

## License
This project is open-source and available under the MIT License.
