---
name: Central Gatekeeper Flow
description: The system logic for the centralized prompt evaluation and security middleware across all platforms.
---

# 🛡️ Central Gatekeeper Flow

The Gatekeeper system acts as the **first line of defense (Middleware)** located on the Center Server.  
It evaluates user prompts received from any integrated Platform Agent before allowing the client or central AI to process the request.

## 📌 Scope
This file covers the workflow from receiving the initial user prompt to the final approval (`GOOD`) or rejection (`BAD`) decision.

## ⚙️ Logic Flow

1. **Request Interception:** 
   - When a user issues a command on a connected platform.
   - The Platform Agent intercepts the command and immediately sends an HTTP POST request to the Center Server's `POST /api/evaluate` endpoint.
2. **Decision Model Evaluation:**
   - The Center Server routes the prompt to a highly efficient `decisions` model alongside a strict security evaluation System Prompt.
   - The model responds strictly with either `GOOD` (Safe/Compliant) or `BAD` (Harmful/Inappropriate/Out-of-bounds).
3. **Fail-Closed Verification:**
   - If the result is `BAD`, or if any system error occurs (e.g., API timeout, model failure), the system defaults to a "Fail-Closed" state, treating the prompt as unsafe by default.
   - The Center Server returns a `Rejected` response to the platform.
4. **Action on Platform:**
   - If Rejected: The Platform Agent notifies the user of the policy violation and immediately halts execution.
   - If Approved (`GOOD`): The Platform Agent proceeds to the reasoning and task delegation phase (See [Multi-Agent Tool Delegation](./tool-delegation.md)).
