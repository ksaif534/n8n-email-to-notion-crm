# Gmail to Notion CRM Workflow

## Overview

This n8n workflow automatically captures contact form submissions from Gmail and adds them to a Notion database, creating a simple but effective CRM system. The workflow monitors your Gmail inbox for messages with "Contact Form" in the subject, extracts the contact information using AI, and creates a new entry in your Notion database.

## Features

- **Automated Email Monitoring**: Checks Gmail inbox every minute for new contact form submissions
- **AI-Powered Data Extraction**: Uses Google Gemini to intelligently parse contact information from emails
- **Structured Data Storage**: Creates organized entries in a Notion database with name, email, message, and date

## Prerequisites

- An n8n instance (local or cloud)
- Gmail account with OAuth2 credentials
- Google Gemini (PaLM) API key
- Notion account with API integration
- A Notion database with the following properties:
  - Name (title)
  - Email (email)
  - Message (rich text)
  - Date (date)

## Setup Instructions

1. Import the `gmail-to-notion-crm.json` workflow into your n8n instance
2. Configure the required credentials:
   - Gmail OAuth2 account
   - Google Gemini (PaLM) API
   - Notion API integration
3. Update the Notion database ID if needed
4. Activate the workflow

## How It Works

1. The Gmail Trigger node monitors your inbox for new emails containing "Contact Form" in the subject
2. When a matching email is found, the Basic LLM Chain node uses Google Gemini to extract the contact information
3. The Code node parses the AI response into a structured JSON format
4. The Notion node creates a new database entry with the extracted information

## Customization

You can customize this workflow by:
- Modifying the Gmail filter to match different email subjects
- Adjusting the AI prompt to extract additional information
- Adding more properties to the Notion database
- Implementing additional processing steps or notifications

## Troubleshooting

If the workflow isn't working as expected:
- Check that all credentials are properly configured
- Verify that your Notion database has the required properties
- Ensure the Gmail filter is correctly set up
- Review the execution logs in n8n for any errors

## License

This workflow is provided as-is under the MIT License.