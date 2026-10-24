---
name: LXAgents Architecture Overview
description: System architecture overview of the LXAgents ecosystem and main directory index.
---

# 🌐 LXAgents Architecture

Welcome to the central architecture documentation for the **LXAgents** project.  
This repository is dedicated to storing and explaining the system logic and structural workflows between the **Center Server** (Centralized API/Brain) and **Platform Agents** (e.g., Game servers, Web applications, Mobile apps, or any connected client environment).

## 🧠 System Context & Core Principles

- **Primary Router (OpenRouter):** OpenRouter currently serves as the core API and routing system for managing agent models across various modalities (text, image, decisions, etc.).
- **Router Agnosticism:** The architecture is highly modular. We can seamlessly swap out OpenRouter for another provider or platform in the future, provided it supports multi-agent routing.
- **Graceful Degradation:** Platform Agents can utilize alternative platforms or local models. If a platform lacks support for a specific agent type or modality, the overall system will not crash; it will continue to function normally with those specific unsupported features gracefully disabled or bypassed.
- **State Independence:** The Center Server does not store platform-specific states or execute local tools. All client-side context remains strictly isolated on the Platform Agent.
- **Fail-Safe Routing:** The central system includes auto-retry logic and dynamic endpoint switching to automatically handle provider limits or errors without interrupting the user experience.

## 📚 Directory Index

- [AGENTS.md](./AGENTS.md) - **Read this first!** Guidelines and rules for creating new documentation files in this repository.
- **Wiki: System Logic**
  - [Central Gatekeeper Flow](./wiki/system/gatekeeper-flow.md) - Centralized prompt evaluation and security middleware.
  - [Multi-Agent Tool Delegation](./wiki/system/tool-delegation.md) - Task separation logic between Local Tools (Client-side) and Global Tools (Server-side).

---
*Note: The documentation structure in this repository strictly follows the principles of Decoupled Architecture and Multi-Agent Delegation.*
