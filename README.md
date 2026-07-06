# CleanTech AI Assistant — Retrieval-Augmented Generation for Clean Technology

An intelligent AI assistant specialized in **clean technology** — renewable energy, electric vehicles, and energy storage — built as a **retrieval-augmented generation (RAG)** system with LangChain and a Llama 2 language model.

This was the final project for CSC 583 (Natural Language Processing).

## Overview

The assistant answers domain questions about clean technology by retrieving relevant passages from a curated clean-tech corpus and generating grounded answers, rather than relying solely on the language model's parametric memory. Reported evaluation: **~85% retrieval accuracy** with strong response quality.

Key components:

- **RAG architecture** — LangChain orchestrates retrieval over a vector store (ChromaDB) and generation with **Llama 2**.
- **Reasoning engine** — surfaces transparent, step-by-step decision-making rather than opaque answers.
- **Ethical guardrails** — checks to keep generated content responsible and on-domain.
- **Conversational memory** — preserves context across multi-turn conversations.

## Data

The corpus and evaluation sets are **not included** in this repository. The project uses a clean-technology media dataset and a companion RAG-evaluation set (question/answer pairs). Point the ingestion step in the notebook at your own copy of the corpus, then build the vector store.

The Chroma vector database (`chroma_db/`) is a generated artifact and is excluded — it is rebuilt when you run the ingestion cells.

## Repository structure

```
.
├── notebooks/
│   └── clean_tech_ai_assistant.ipynb   # Ingestion, vector store, RAG chain, reasoning, evaluation
├── results/
│   ├── 1.png
│   ├── 2.png
│   └── Figure_1.png                    # Evaluation / analysis plots
├── reports/
│   └── Report.pdf                      # Project write-up
├── requirements.txt
└── README.md
```

## Getting started

1. Clone the repository and create a virtual environment:

   ```bash
   git clone https://github.com/<your-username>/CleanTech-AI-Assistant.git
   cd CleanTech-AI-Assistant
   python3 -m venv .venv && source .venv/bin/activate
   pip install -r requirements.txt
   ```

2. Provide your clean-tech corpus and set any model/API configuration required by the notebook (e.g. a Llama 2 endpoint or local weights).

3. Run the notebook to ingest documents, build the ChromaDB store, and query the assistant:

   ```bash
   jupyter notebook notebooks/clean_tech_ai_assistant.ipynb
   ```

## Requirements

- Python 3.10+
- LangChain, ChromaDB
- A Llama 2 model (local weights or a hosted endpoint)
- NumPy, pandas, scikit-learn, matplotlib, seaborn

See `requirements.txt`.

## Author

Krishnarjun Lakshminarayanan — CSC 583 Natural Language Processing.
