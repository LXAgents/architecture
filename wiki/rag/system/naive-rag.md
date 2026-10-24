---
name: Naive RAG
description: The foundational RAG pattern using simple vector search.
---

## Overview

This is the most basic RAG architecture. Documents are divided into smaller chunks, converted into vector representations using an Embedding model, and stored in a Vector Database. It is fast and easy to set up but may lack precision for complex queries.

## Logic Flow

1. **User submits a Query** — The user provides a natural language question or request.
2. **Query Embedding** — The Query is embedded into a vector using an Embedding model.
3. **Similarity Search** — The system performs a similarity search in the Vector Database to retrieve relevant chunks (Context).
4. **Prompt Construction** — The retrieved Context is combined with a Prompt template.
5. **Response Generation** — The Generative model processes this combined prompt to output a Response.

## Characteristics

- **Speed**: Fast retrieval and generation
- **Setup Complexity**: Low — easy to implement and maintain
- **Precision**: May lack precision for complex or ambiguous queries
- **Use Case**: Suitable for straightforward Q&A over document collections