
# Arman — AI-Powered Enterprise Knowledge Management

An AI-powered knowledge management MVP designed to help organizations retrieve information from internal documents and receive reliable, source-grounded answers.

Arman uses an Agentic Retrieval-Augmented Generation (RAG) architecture that combines document retrieval, evidence evaluation, and LLM-based response generation.

> «Project Status: MVP / Experimental
> The system has been evaluated in laboratory settings but has not yet been deployed or tested with real organizational users.»

---

## 🎥 Product Demo

["Watch the product demo"](ADD_DEMO_LINK_HERE)

<!-- Add product screenshots below -->
<p align="center">
  <img src="assets/screenshots/screenshot-1.png" width="45%" />
  <img src="assets/screenshots/screenshot-2.png" width="45%" />
</p>

---

## The Problem

Organizational knowledge is often scattered across documents, reports, and internal resources. Finding reliable information can be time-consuming and may create dependency on domain experts.

Arman was developed to explore how an AI-powered knowledge management system could help employees access organizational knowledge more efficiently through natural language while keeping answers grounded in source documents.

---

## Key Features

- AI-powered question answering over organizational documents
- Agentic RAG workflow for managing the response process
- Hybrid and dense retrieval strategies
- Semantic search using vector embeddings
- Keyword retrieval using BM25
- Evidence-based response generation
- Source and document reference tracking
- Abstention when sufficient evidence is unavailable
- Persian-language conversational interface

---

## System Architecture

The system follows an Agentic RAG architecture:

```

User Query
│
▼
Agent / Decision Layer
│
├── Evaluate retrieved evidence
├── Decide whether to answer or abstain
└── Manage the response workflow
│
▼
Retrieval Engine
│
├── Dense Retrieval
└── BM25 Keyword Retrieval
│
▼
Ranking / Fusion
│
▼
Knowledge Base
(ChromaDB + Metadata)
│
▼
LLM
│
▼
Source-Grounded Response

```

The agent orchestration layer was designed to manage the response process and evaluate whether sufficient evidence exists before generating an answer.

---

## Technical Highlights

### Retrieval Pipeline

The system supports multiple retrieval strategies:

- Dense Retrieval using vector embeddings
- Keyword Retrieval using BM25
- Hybrid Retrieval combining dense and keyword search
- Weighted Reciprocal Rank Fusion (RRF) for combining retrieval results

The knowledge base uses ChromaDB for vector storage and retrieval, with metadata support for source tracking.

### Embeddings and Document Processing

The system uses BAAI/bge-m3, a multilingual embedding model suitable for Persian-language content.

The document preparation pipeline includes:

- Text cleaning and preprocessing
- Document chunking with overlap
- Metadata management
- Vector indexing

### Agentic Workflow

An agent-based orchestration layer built with LangGraph manages different stages of the response process, including evidence evaluation and response decisions.

The system can abstain from answering when sufficient supporting evidence is not available in the knowledge base.

---

## Evaluation

The MVP was evaluated in laboratory settings using internal benchmark datasets and automated evaluation methods.

### Response Quality Evaluation

Response quality was evaluated on a dataset of 200 questions using the DeepEval framework and an independent evaluator model.

| Metric | Result |
|---|---|
| Faithfulness / Grounding | 0.9527 |
| Answer Relevance | 0.8072 |
| Citation Accuracy | 0.9333 |
| Abstention Accuracy | 0.98 |
| False Abstention Rate | 4% |
| False Answer Rate | 2% |
| Average End-to-End Latency | 3 seconds |

These results indicate strong grounding and citation performance under the project's experimental evaluation setup.

### Retrieval Benchmark

The retrieval engine was evaluated using 139 human-written questions derived from an organizational FAQ dataset.

| Retrieval Method | MRR | Hit@10 |
|---|---|---|
| Dense Retrieval | 0.957 | 1.000 |
| Hybrid Retrieval | 0.939 | 1.000 |
| BM25 | 0.848 | 0.978 |

For the evaluated dataset, dense retrieval achieved the highest MRR, while both dense and hybrid retrieval achieved full Hit@10 coverage.

> «Evaluation Limitations: These results were obtained in laboratory settings using internal benchmark datasets. The system has not yet been deployed in a real organizational environment, and real-user testing, load testing, and concurrent-user evaluation have not yet been conducted.»

---

## My Contribution

I served as the Team Lead for a two-person team and contributed to both the product and technical development of the project.

My responsibilities included:

- Product backlog management and prioritization
- Contributing to problem discovery and validation planning
- Backend development using Python and FastAPI
- Knowledge base design and management
- Document processing and retrieval pipeline implementation
- Implementing and evaluating RAG system components
- Database design and documentation
- Contributing to the overall system architecture

The frontend and agent core were developed collaboratively by the project team.

---

## Tech Stack

### AI & Backend

- Python
- FastAPI
- LangGraph
- LLM APIs
- BAAI/bge-m3

### Retrieval & Data

- ChromaDB
- BM25
- Dense Retrieval
- Hybrid Search
- Weighted RRF

### Evaluation

- DeepEval
- LLM-based evaluation

### Frontend

- React
- Vite
- Tailwind CSS

---

## Future Directions

Potential areas for further development include:

- Customer discovery and validation with real organizational users
- Deployment and testing in a real organizational environment
- Load and concurrent-user testing
- Integration with organizational tools such as Jira, CRM, and ERP systems
- Advanced reranking methods
- Role-based access control and administrative tools
- Knowledge graph integration

---

## Project Context

Arman was developed as an MVP during an innovation bootcamp to explore the potential of AI-powered enterprise knowledge management.

The project demonstrated the technical feasibility of the proposed approach through laboratory evaluation. Further development would require customer discovery and real-world validation to better understand organizational needs and evaluate product-market fit.
