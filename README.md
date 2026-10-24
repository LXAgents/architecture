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
- **Bring Your Own Key (BYOK) & Zero-Cost Scaling:** The Center Server operates as a stateless, multi-tenant SaaS middleware. Connected platforms must provide their own API keys dynamically (e.g., via HTTP headers) for each request. This ensures infinite scalability, zero centralized API token costs, and strict security isolation per platform.
- **Graceful Degradation:** Platform Agents can utilize alternative platforms or local models. If a platform lacks support for a specific agent type or modality, the overall system will not crash; it will continue to function normally with those specific unsupported features gracefully disabled or bypassed.
- **State Independence & Data Persistence:** The Center Server acts exclusively as a routing gateway and does not retain or store any data. Consequently, each connected platform must implement and manage its own logic for data saving, memory, and state persistence locally.
- **Fail-Safe Routing:** The central system includes auto-retry logic and dynamic endpoint switching to automatically handle provider limits or errors without interrupting the user experience.

## 🔀 Supported Agent Modalities

The central routing system is capable of handling 9 types of agent modalities. Click on each modality below for detailed specifications and routing logic:

- [Text](./wiki/model/text.md)
- [Image](./wiki/model/image.md)
- [Video](./wiki/model/video.md)
- [Speech](./wiki/model/speech.md)
- [Decisions](./wiki/model/decisions.md)
- [Embeddings](./wiki/model/embeddings.md)
- [Rerank](./wiki/model/rerank.md)
- [Transcription](./wiki/model/transcription.md)
- [Audio](./wiki/model/audio.md)

## 📚 Directory Index

- [AGENTS.md](./AGENTS.md) - **Read this first!** Guidelines and rules for creating new documentation files in this repository.
- **Wiki: System Logic**
  - [Central Gatekeeper Flow](./wiki/system/gatekeeper-flow.md) - Centralized prompt evaluation and security middleware.
  - [Multi-Agent Tool Delegation](./wiki/system/tool-delegation.md) - Task separation logic between Local Tools (Client-side) and Global Tools (Server-side).

---
*Note: The documentation structure in this repository strictly follows the principles of Decoupled Architecture and Multi-Agent Delegation.*
