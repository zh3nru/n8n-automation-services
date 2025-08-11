# n8n Automated Services

This repository contains n8n workflows designed to automate common data processing tasks across Gmail, Google Sheets, Google Drive, and Telegram, with the use of the AI model Google Gemini.

## [Gmail Email Processing & Organization](https://github.com/zh3nru/n8n-automation-services/blob/main/gmail-sheets-drive-workflow.json)

**Purpose:**  
Automatically monitor a Gmail inbox, categorize unlabeled emails using Google Gemini, store key data in Google Sheets, and organize attachments in Google Drive.

**Process Overview:**
1. **Inbox Monitoring:**  
   - Checks Gmail at predefined intervals.
   - Monitors multiple labels (e.g., `label1`, `label2`, `label3`).
   - If an email has no label, assigns one automatically using **Google Gemini**.

2. **Data Extraction & Storage:**  
   - Extracts sender information.
   - Inserts details into a designated **Google Sheet**.

3. **Attachment Handling:**  
   - Downloads all attachments to **Google Drive**.
   - Groups attachments in folders by:
     - **Sender Name**
     - **Label**
     - **Date Received**

## [Telegram Receipt Processing](https://github.com/zh3nru/n8n-automation-services/blob/main/telegram-sheets-drive-workflow.json)

**Purpose:**  
Accept receipt photos from Telegram, use Google Gemini to extract key information, and store both the structured data and the original images.

**Process Overview:**
1. **Telegram Intake:**  
   - Receives receipt photos sent via a Telegram bot.

2. **AI Data Extraction:**  
   - Uses **Google Gemini** to extract:
     - Merchant Name
     - Merchant Location
     - Amount
     - Date
     - Item name
     - Item quantity
     - Payment Nethod
     - Total Price/Amount

3. **Data Storage:**  
   - Appends extracted details to a designated **Google Sheet**.

4. **Photo Storage:**  
   - Saves the original image to **Google Drive**.
   - Organizes photos in folders by **Date Received**.

## Requirements

- [n8n](https://n8n.io/)
- Gmail API access
- Google Sheets API access
- Google Drive API access
- Telegram Bot API token
- Google Gemini API key

## Usage Notes

- Import the workflow JSON files into your n8n instance.
- Set up credentials for:
  - Gmail
  - Google Sheets
  - Google Drive
  - Telegram
  - Google Gemini
- Adjust labels, folder paths, and Google Sheet rows and IDs as needed.
- Configure trigger intervals to match your specific needs.
