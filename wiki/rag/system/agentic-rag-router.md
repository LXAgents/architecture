---
name: Agentic RAG (Router)
description: Dynamic RAG system using an AI Agent to route queries to the best source.
---

## Overview

In this setup, a central AI Agent acts as a Router. It evaluates the user's intent and dynamically decides which data source (Vector DB, Graph DB, or Web search) is best suited to answer the specific query, offering high flexibility for varied use cases.

## Logic Flow

1. **User submits a Query** — The user provides a natural language question or request.
2. **Intent Analysis** — The AI Agent (Router) analyzes the Query to understand intent and requirements.
3. **Source Routing** — The Router directs the Query to the appropriate source (Vector Database, Graph Database, or Web Search).
4. **Prompt Construction** — The retrieved Context from the selected source is combined with a Prompt template.
5. **Response Generation** — The Generative model formulates the Response.

## Characteristics

- **Dynamic Routing**: Automatically selects optimal data source per query
- **Flexibility**: Handles diverse query types without manual configuration
- **Extensibility**: Easy to add new data sources to the routing logic
- **Use Case**: Heterogeneous knowledge bases, varying query complexity, multi-source environments