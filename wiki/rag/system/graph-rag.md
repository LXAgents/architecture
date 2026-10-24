---
name: Graph RAG
description: RAG architecture utilizing Knowledge Graphs for relational context.
---

## Overview

Instead of relying solely on vector similarity, this pattern uses an LLM graph generator to extract entities and relationships from documents, storing them in a Graph Database. It excels at answering questions that require connecting multiple dots across different documents.

## Logic Flow

1. **Graph Construction** — Documents are processed by an LLM graph generator to build a Graph Database of entities and relationships.
2. **User submits a Query** — The user provides a natural language question.
3. **Graph Query** — The LLM graph generator queries the Graph Database to extract a relational Context relevant to the query.
4. **Prompt Construction** — The relational Context is combined with a Prompt template.
5. **Response Generation** — The Generative model outputs the Response based on the connected data.

## Characteristics

- **Relational Reasoning**: Excels at multi-hop questions connecting entities across documents
- **Structured Knowledge**: Explicit entity-relationship representation
- **Explainability**: Clear traceability of how answers are derived
- **Use Case**: Complex queries requiring synthesis across multiple documents, knowledge graph construction