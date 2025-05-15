# 🤖 AI Support Agents with n8n + OpenAI

This repository contains two workflows built with [n8n](https://n8n.io/) that create AI-powered customer support experiences — one via **web chat** and another via **WhatsApp** — both integrated with **Google Sheets** to log conversations and user data.

## 📁 Workflows Overview

### 1️⃣ AI Web Chat (`AgenteChat`)

This workflow enables real-time interaction with an AI via a web-based chat. Here's how it works:

- A user sends a message through the web interface.
- The message and session ID (`chatId`) are captured.
- These are logged to a specific tab in a Google Sheets document.
- The message is processed by an AI agent with:
  - **Contextual memory**
  - Access to **Wikipedia** and a **calculator**
  - A **friendly, emoji-rich personality** to humanize responses
- The AI response is returned to the user on the web chat.

📄 Spreadsheet: [Google Sheet - Case 1](https://docs.google.com/spreadsheets/d/1OCJq36xYq2kzEhur8H2Tv-aRp5VRy-ZMtc0aDM2Zv-o/edit#gid=0)

---

### 2️⃣ AI WhatsApp Bot (`AgenteWhatsApp`)

This workflow simulates an automated WhatsApp assistant using AI. It functions as follows:

- The user sends a message via WhatsApp.
- The workflow filters out messages from groups, newsletters, or APIs.
- The sender’s name, phone number, and message are extracted.
- Contact info is **stored and updated** in a Google Sheet.
- The message is passed to the same intelligent agent used in the web chat.
- The AI response is sent back to the WhatsApp number using an external API (e.g., Z-API).

📄 Spreadsheet: [Google Sheet - Case 2](https://docs.google.com/spreadsheets/d/1OCJq36xYq2kzEhur8H2Tv-aRp5VRy-ZMtc0aDM2Zv-o/edit#gid=1727923156)

---

## 🧠 AI Agent Features

Both workflows use OpenAI's `gpt-4o-mini` model integrated via `@n8n/n8n-nodes-langchain`, and include:

- **Session-based memory**, tracked by chat ID or phone number
- Access to support tools:
  - 📚 **Wikipedia** for factual queries
  - 🧮 **Calculator** for math operations
- A system prompt that ensures the agent is:
  - Polite
  - Funny
  - Humanized (uses emojis 🎉)

---

## 🛠 Tech Stack

- [n8n](https://n8n.io/) — Low-code workflow automation
- [OpenAI GPT-4o](https://openai.com/gpt-4o) — Language model for conversation
- [Google Sheets](https://www.google.com/sheets/about/) — Used for storing messages and contacts
- [Z-API](https://z-api.io/) — WhatsApp integration (via webhook + HTTP request)

---

## ⚙️ Notes

- You need to configure your **Google Sheets and OpenAI credentials** in n8n for the flows to work.
- WhatsApp bot requires a connected API service (e.g., Z-API).
- The WhatsApp workflow is currently **inactive** (`"active": false`) — activate it when ready.

---

## 🚀 Get Started

Clone this repo, import the `.json` workflows into your n8n instance, set up the required credentials, and start delivering automated AI-powered support!