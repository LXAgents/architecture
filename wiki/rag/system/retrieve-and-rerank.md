---
name: Retrieve-and-rerank
description: RAG pattern with an added ranking layer for higher precision.
---

## Overview

An evolution of Naive RAG designed to reduce hallucination and improve accuracy. After the initial retrieval from the Vector Database, a dedicated Ranker model evaluates and re-orders the retrieved chunks based on their actual relevance to the query.

## Logic Flow

1. **User submits a Query** — The user provides a natural language question or request.
2. **Initial Retrieval** — Initial retrieved chunks are pulled from the Vector Database using similarity search.
3. **Re-ranking** — A Ranker model evaluates these chunks and creates Re-ranked context, ordering them by true relevance to the query.
4. **Prompt Construction** — The highly relevant Re-ranked context is combined with a Prompt template.
5. **Response Generation** — The Generative model generates the Response using the refined context.

## Characteristics

- **Accuracy**: Higher precision than Naive RAG due to re-ranking
- **Hallucination Reduction**: Significantly reduced by filtering irrelevant chunks
- **Latency**: Slightly higher than Naive RAG due to the re-ranking step
- **Use Case**: Ideal when accuracy is critical and queries may retrieve noisy results