---
name: Agent RAG (Multi-Agent RAG)
description: Complex RAG architecture utilizing multiple specialized AI agents.
---

## Overview

The most advanced pattern. A primary AI Agent delegates tasks to various sub-agents. These sub-agents simultaneously query multiple internal and external tools (e.g., Vector engines, Web search, Slack, Gmail). It is ideal for deep research and complex workflows but has high latency and API costs.

## Logic Flow

1. **User submits a Query** — The user provides a natural language question or complex task.
2. **Task Decomposition** — The Main AI Agent interprets the task and breaks it down into subtasks.
3. **Agent Dispatch** — The Main Agent dispatches requests to Sub AI Agents.
4. **Parallel Tool Execution** — Sub-agents interact with diverse Tools (Vector Search A/B, Web Search, Slack, Gmail, etc.) to gather comprehensive context.
5. **Response Synthesis** — The gathered information is compiled, and a final Generative model produces the Response.

## Characteristics

- **Deep Research Capability**: Suited for complex, multi-step investigations
- **Tool Diversity**: Integrates with many internal and external systems
- **Parallel Execution**: Sub-agents work simultaneously for efficiency
- **High Cost/Latency**: Significant API usage and processing time
- **Use Case**: Deep research assistants, complex workflow automation, cross-system intelligence