# 🤖 PRD Generator Agent – n8n Workflow

This repository contains an automated n8n workflow that reads project information from a Google Sheet and generates a detailed, formatted Product Requirements Document (PRD) using Google's Gemini LLM. It also identifies tools used in the agent, and documents each tool’s usage, input, and output format in a well-formatted Google Doc.

---

## 🚀 Features

- ✅ Reads project data from Google Sheets row by row
- 🧠 Generates a full PRD using Gemini LLM and a smart template
- ✨ Reformats the PRD for readability and structure
- 🔍 Extracts tools mentioned and generates usage details
- 📄 Creates and updates a structured PRD document in Google Docs
- 🛑 Stops gracefully if required fields are blank

---

## 📁 Files Included

| File | Description |
|------|-------------|
| `prd-generator-workflow.json` | The n8n workflow (credentials removed, safe for sharing) |
| `README.md` | Documentation for this repo |
| `.env.example` | Placeholder for required environment variables |
| `assets/` | (Optional) Folder containing screenshots or diagrams |

---

## 📷 Workflow Diagram

![Workflow Diagram](assets/prd_generator_workflow.png)

---

## ⚙️ Requirements

- An [n8n](https://n8n.io) instance (Cloud or Self-hosted)
- Active Google Workspace account with:
  - Google Sheets access
  - Google Docs access
- Gemini (PaLM) API key or equivalent LLM
- The following n8n credentials set up:
  - `Google Sheets OAuth2`
  - `Google Docs OAuth2`
  - `Gemini/Google Palm API`

---

## 🧠 How It Works

1. **Trigger Manually** → via button (`Manual Trigger`)
2. **Read** each row from a Google Sheet
3. **Check** if data like `description` exists; stop if blank
4. **Generate** PRD using Gemini LLM and template
5. **Format** the markdown into plain text with readable layout
6. **Analyze Tools** listed and describe:
   - Use
   - Inputs
   - Outputs
7. **Create Google Doc** and **Insert** PRD and Tool summary

---

## 📄 Example Input (Google Sheet)

| agentName      | description           | whyNeeded           | targetUsers | triggerMechanism | toolsInUse         |
|----------------|-----------------------|----------------------|-------------|------------------|---------------------|
| Expense Agent  | Auto-categorizes bills | Manual tagging wastes time | Finance team | Invoice Upload | OCR, Expense DB, Policy Engine |

---

## ✍️ Example Output (Google Doc)

The generated PRD includes:

- PRD structure: agent name, description, trigger, logic, etc.
- Plain-text formatting (no markdown syntax)
- Tool documentation section:

