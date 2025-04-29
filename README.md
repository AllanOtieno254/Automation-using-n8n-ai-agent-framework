# 🏠 Home Inventory Management AI Assistant using n8n

This project is a smart inventory tracking assistant built with **n8n**, integrating AI chat, memory management, and a dynamic inventory database (via Airtable). The assistant uses natural language to help users monitor household item levels and alerts when items fall below a predefined threshold (e.g., 5%).
![Home inventory](https://github.com/user-attachments/assets/844530ae-ac57-4b78-9c24-9d0c50757a7a)

---

## 🚀 Features

- 📦 **Inventory Threshold Tracking:** Automatically identifies items below a 5% stock level.
- 🧠 **AI-Powered Assistant:** Uses DeepSeek (or any LLM) to process messages and respond helpfully.
- 🔁 **Memory Integration:** Keeps context between interactions using the `Simple Memory` module.
- 📊 **Airtable Database Connection:** Retrieves inventory records in real-time.
- 💬 **Chat Trigger Interface:** Allows user to interact through natural language.

---


## 🔄 Workflow Details
Trigger Node: Activated when a chat message is received.

AI Agent Node: Orchestrates:

Sends user prompt and context to a language model.

Loads memory (context) from previous sessions.

Retrieves inventory data from Airtable.

DeepSeek Chat Model Node: Processes and formats AI response.

Airtable Node: Pulls latest stock levels for all inventory items.

Simple Memory Node: Loads and saves memory for context-aware responses.



## 🧩 Workflow Overview

```mermaid
graph TD
    A[🟢 Trigger: Chat Message Received] --> B[🧠 AI Agent]
    B --> C[🤖 DeepSeek Chat Model]
    B --> D[💾 Simple Memory]
    B --> E[📋 Airtable Search]

    subgraph Tools
        C
        D
        E
    end
