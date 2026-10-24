---
name: Multi-Agent Tool Delegation
description: The logic for separating and delegating tasks between platform-specific Local Tools and central Global Tools.
---

# 🤖 Multi-Agent Tool Delegation

This architecture utilizes an **Agent-to-Agent Delegation** pattern to strictly decouple responsibilities between the Center Server and connected Platform Servers.

## 📌 Scope
This file explains the reasoning and routing logic of the Platform Agent after a prompt has passed the Gatekeeper, detailing how it decides whether to execute a task locally or delegate it to the Center Server.

## ⚙️ Logic Flow

### 1. Platform Agent (Client-Side Brain)
The Platform Agent is the AI embedded within a specific client application or platform.  
It only has knowledge of its **Local Tools** (platform-specific actions and state mutations).
- **Examples of Local Tools:** `trigger_client_event`, `update_ui_element`, `modify_local_database`.
- **Bridge Tool:** Every Platform Agent is equipped with a universal tool named `ask_global_center` to request assistance from the central server.

### 2. Reasoning & Routing
Once the Platform Agent receives an approved prompt, it analyzes the requirements:
- **Internal Task:** (e.g., *"Change the background color to red."*)
  - The Agent directly calls the Local Tool `update_ui_element("background", "red")` and completes the task entirely within the client environment.
- **External / Knowledge Task:** (e.g., *"Summarize the latest financial news."*)
  - The Agent realizes it lacks global knowledge or access to external APIs, so it invokes the Bridge Tool: `ask_global_center("Fetch and summarize financial news")`.
- **Hybrid Task:** (e.g., *"Search for today's weather and display it as a local notification."*)
  - The Agent calls `ask_global_center` to fetch the weather data.
  - Upon receiving the central server's response, the Agent concurrently executes its Local Tool `trigger_client_event("notification", weather_data)` to display it to the user.

### 3. Center Server (Central Brain)
When the Center Server receives a request via the `ask_global_center` tool:
- It acts as the primary master Agent equipped with **Global Tools** (e.g., `web_search`, `rag_query`, `database_lookup`, `image_generation`).
- It autonomously executes the necessary central tools, gathers the information, and finalizes the output.
- The finalized result (text, JSON, or media references) is returned to the Platform Agent to be presented or utilized locally.
