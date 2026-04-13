# LightRAG Exploration

A graph-based Retrieval-Augmented Generation (RAG) system that combines knowledge graphs with vector search for smarter, more context-aware document Q&A.

Built on top of the [HKUDS/LightRAG](https://github.com/HKUDS/LightRAG) open-source project (MIT License) as a hands-on learning exercise.

---

## Why I Built This

I came across LightRAG while exploring the latest RAG architectures and wanted to understand how GraphRAG compares to naive vector search in practice. The idea of combining knowledge graphs with embeddings, so the system understands relationships between concepts, not just similarity.

I set this up over a weekend to get hands-on experience with the full stack: from ingesting documents, to building the knowledge graph, to querying it with different retrieval modes.

---

## What is LightRAG?

Most RAG systems work like this: split documents into chunks → embed them → retrieve the most similar chunks → send to LLM. Simple, but it loses context and relationships.

LightRAG goes further by building a **knowledge graph** on top of your documents:

- Entities and relationships are extracted and stored as graph nodes/edges
- Queries can retrieve information using **4 modes**:
  - `naive` – standard chunk retrieval
  - `local` – entity-focused, finds specific facts
  - `global` – relationship-focused, understands connections
  - `hybrid` – combines local + global for best results

This makes it especially powerful for complex document corpora where context and relationships matter — exactly the kind of evaluation and knowledge management work done at organisations like IFAD.

---

## Stack

| Layer | Technology |
|---|---|
| Core RAG engine | [LightRAG](https://github.com/HKUDS/LightRAG) |
| LLM | OpenAI GPT-4o-mini |
| Embeddings | OpenAI `text-embedding-3-small` |
| Vector store | NanoVectorDB (built-in) / compatible with Neo4j |
| Graph storage | NetworkX (local) |
| Web UI | LightRAG WebUI |
| Deployment | Docker / docker-compose |
| Language | Python 3.11+ |

---

## Key Learnings

Working through this project gave me hands-on experience with:

- **GraphRAG architecture** — understanding how entity extraction + graph traversal improves retrieval over naive similarity search
- **RAG evaluation** — experimenting with different query modes and observing how `hybrid` retrieval outperforms `naive` for multi-hop questions
- **Full-stack AI tooling** — connecting LLM APIs, vector stores, graph databases, and a React-based WebUI
- **Containerisation** — deploying the full stack with Docker Compose, including GPU-aware configuration options

---

## Relevance to Evaluation & Knowledge Management

RAG systems like this have direct applications in evaluation work as querying a corpus of hundreds of evaluation reports and getting answers that understand the relationships between findings, recommendations, and outcomes, not just keyword matches. That's the kind of AI-for-impact potential that motivated this project.

---

## License & Attribution

This project is built on [LightRAG](https://github.com/HKUDS/LightRAG) by HKUDS, licensed under the [MIT License](LICENSE). All original work and intellectual property belongs to the original authors.

---

*Part of my ongoing exploration of Generative AI and RAG systems. See also my [GitHub profile](https://github.com/shkamila) for other projects.*
