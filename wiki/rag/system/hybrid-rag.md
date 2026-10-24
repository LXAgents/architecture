---
name: Hybrid RAG
description: An advanced pattern combining Vector and Graph databases.
---

## Overview

This pattern merges semantic search (Vector DB) with relational search (Graph DB). Documents are processed into both databases simultaneously. It provides comprehensive enterprise-level knowledge retrieval but requires complex architecture and high compute resources.

## Logic Flow

1. **Dual Processing** — Documents are processed by both an Embedding model (to Vector DB) and an LLM graph generator (to Graph DB).
2. **User submits a Query** — The user provides a natural language question.
3. **Dual Retrieval** — The system retrieves semantic context from the Vector DB and relational context from the Graph DB.
4. **Context Merging** — Both contexts are merged into a unified Prompt template.
5. **Response Generation** — The Generative model produces a highly accurate and contextual Response.

## Characteristics

- **Comprehensive Coverage**: Combines semantic similarity with relational reasoning
- **Enterprise-Grade**: Suitable for complex knowledge management systems
- **Resource Intensive**: Requires maintaining two database systems and dual processing pipelines
- **Use Case**: Large-scale enterprise knowledge bases, complex analytical queries