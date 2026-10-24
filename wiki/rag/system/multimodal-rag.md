---
name: Multimodal RAG
description: RAG system capable of processing text, images, and other media.
---

## Overview

This pattern extends RAG to support Multimodal Documents (e.g., text, images, slides). It uses a Multimodal Embedding model to store diverse data types in the Vector Database and a Multimodal Generative model to understand and generate responses across different media types.

## Logic Flow

1. **Document Processing** — Multimodal documents are chunked and embedded via a Multimodal Embedding model into the Vector Database.
2. **Query Submission** — User submits a Query, potentially including Media (like an image) alongside text.
3. **Context Retrieval** — The system retrieves relevant multimodal context from the Vector Database based on the query.
4. **Multimodal Generation** — A Multimodal Generative model processes the text query, media input, and retrieved context to formulate a Response.

## Characteristics

- **Media Support**: Handles text, images, slides, and other media types
- **Unified Embedding**: Single embedding space for multiple modalities
- **Rich Responses**: Can reference and reason about visual content
- **Use Case**: Document analysis with diagrams, chart interpretation, mixed-media knowledge bases