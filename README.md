
# Email Agent 📧

An AI-powered email automation agent built with n8n that automatically classifies incoming Gmail emails and drafts intelligent replies using Groq LLM.

## What it does

- Monitors Gmail inbox via Gmail Trigger
- Classifies emails into two categories: **Order** or **Inquiry** using a Text Classifier
- Automatically drafts appropriate replies using Groq AI
- Saves drafted replies back to Gmail (create: draft) for review before sending

## Workflow Overview
Gmail Trigger → Text Classifier → [Order path] → Groq (Order) → Draft Order Reply → Send Order Draft
→ [Inquiry path] → Groq (Inquiry) → Draft Inquiry Reply → Send Inquiry Draft

## Tools & Services Used

| Tool | Purpose |
|------|---------|
| Gmail Trigger | Monitors inbox for new emails |
| Text Classifier | Classifies email type (Order/Inquiry) |
| Groq (Classifier) | LLM model for classification |
| Groq (Order) | Drafts replies for order emails |
| Groq (Inquiry) | Drafts replies for inquiry emails |
| Gmail (Draft) | Saves AI-generated drafts to Gmail |

## Prerequisites

- n8n instance (cloud or self-hosted)
- Gmail account + Gmail OAuth2 credentials
- Groq API key (free at [console.groq.com](https://console.groq.com))

## How to Import

1. Download `workflow.json` from this repo
2. Open n8n → **Workflows** → **Import from File**
3. Select `workflow.json`
4. Add your credentials:
   - Gmail OAuth2
   - Groq API key
5. Activate the workflow
## How it Works

1. **Gmail Trigger** watches your inbox for new emails
2. **Text Classifier** (powered by Groq) reads the email and decides if it's an Order or an Inquiry
3. Based on the category, the relevant **Groq model** drafts a professional reply
4. The draft is saved to your **Gmail Drafts** folder — you review and send manually

## ⚠️ Important Notes

- This agent creates **drafts only** — it does NOT auto-send emails
- Always review drafts before sending
- Make sure to add your own Gmail and Groq credentials after importing
- Never share your API keys or credentials

## Author

Made by [Syed Najam Ul Hassan] — feel free to fork and customize!

