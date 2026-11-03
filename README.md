# AnimalRAG

## Project Overview

**AnimalRAG** is a planned intelligent information system based on Retrieval-Augmented Generation (RAG) for searching information about animals and answering user questions. The system will use 500 English-language articles from Simple English Wikipedia, selected by animal-related topics.

The user will ask questions in English through a command-line interface (CLI). The system will retrieve the most relevant document fragments and generate an answer that cites its sources.

Example:

```
Question: What do giant pandas eat?
Expected answer: Giant pandas mainly eat bamboo. [Source: Giant panda]
```

> **Note:** This repository currently contains only the project design and initial workspace structure (Lab 1). The RAG system itself is not implemented yet.

## Use Case

**Target audience:**

- Students
- Teachers
- Animal enthusiasts

**Example user questions:**

- What do pandas eat?
- Where do polar bears live?
- How long do elephants live?

## Dataset

| Property | Value |
|----------|-------|
| Source | Simple English Wikipedia |
| Hugging Face dataset | `wikimedia/wikipedia` |
| Configuration | `20231101.simple` |
| Planned corpus | 500 articles |
| Language | English |

Dataset link: https://huggingface.co/datasets/wikimedia/wikipedia

**The actual selection of documents has not been performed yet.** No data has been downloaded.

## Technology Stack

This is the stack **chosen for the future implementation**. It is not an installed or working system.

| Component | Technology | Purpose |
|-----------|------------|---------|
| Programming language | Python 3.11+ | Implementation of all pipeline components |
| Vector database | ChromaDB | Storage and similarity search of document embeddings |
| Embedding model | `sentence-transformers/all-MiniLM-L6-v2` | Converting text fragments and queries into vectors |
| Language model | Llama 3.2 3B | Generating answers from retrieved context |
| LLM runtime | Ollama | Running the language model locally |
| Dataset | Simple English Wikipedia (`wikimedia/wikipedia`, `20231101.simple`) | Knowledge source |
| Dataset size | 500 documents (planned) | Size of the corpus |
| User interface | CLI | Asking questions and showing answers |
| Version control | Git | Source code history |
| Repository hosting | GitHub | Publishing the project |

## System Architecture

1. **Data Ingestion Pipeline** — loads the selected Simple English Wikipedia articles, cleans them and splits them into fragments (chunks).
2. **Embedding Model** — converts chunks and user questions into vector representations.
3. **Vector Database** — stores the chunk embeddings together with source metadata (article title) and supports similarity search.
4. **Retriever** — finds the chunks most relevant to the user question.
5. **LLM** — generates an answer based only on the retrieved context.
6. **Output Validator** — checks that the answer is grounded in the retrieved context and contains references to sources.
7. **CLI Interface** — accepts questions from the user and displays the answer with source citations.

## Project Structure

```
rag-animal-project/
├── src/
│   ├── ingestion/
│   ├── embeddings/
│   ├── retrieval/
│   ├── generation/
│   └── validation/
├── config/
├── reports/
│   └── lab-1/
│       └── README.md
├── tests/
├── README.md
└── .gitignore
```

| Path | Purpose |
|------|---------|
| `src/ingestion/` | Dataset loading, cleaning and chunking (planned) |
| `src/embeddings/` | Embedding generation (planned) |
| `src/retrieval/` | Vector store access and search (planned) |
| `src/generation/` | Answer generation with the LLM (planned) |
| `src/validation/` | Validation of generated answers (planned) |
| `config/` | Configuration files |
| `reports/lab-1/` | Report materials for Lab 1 |
| `tests/` | Automated tests (planned) |

Empty directories contain a `.gitkeep` file so that Git tracks them.

## Installation and Setup

> These are instructions for the **future implementation**. There is no ready-to-run application at the Lab 1 stage.

1. Install Python 3.11+.
2. Clone the repository:

   ```bash
   git clone https://github.com/NureHorishniaKateryna/rag-animal-project.git
   cd rag-animal-project
   ```

3. Create a virtual environment:

   ```bash
   python3 -m venv .venv
   ```

4. Activate the virtual environment:

   ```bash
   # macOS / Linux
   source .venv/bin/activate
   # Windows (PowerShell)
   .venv\Scripts\Activate.ps1
   ```

5. Install the dependencies required by the chosen stack:

   ```bash
   pip install chromadb sentence-transformers datasets ollama
   ```

6. Install Ollama from https://ollama.com/download.
7. Download the Llama 3.2 3B model:

   ```bash
   ollama pull llama3.2:3b
   ```

## Current Status

**Lab 1 — Software Design and Project Initialization.**

- [x] Project name, use case, dataset and technology stack defined
- [x] Directory structure created
- [x] README and Lab 1 report description prepared
- [x] Git repository initialized
- [ ] Final PDF report added to `reports/lab-1/`
- [ ] Documents selected and corpus loaded (not done)
- [ ] Embeddings generated and vector index built (not done)
- [ ] Ollama and Llama 3.2 3B installed (not done)
- [ ] RAG pipeline and CLI implemented (not done)

## Author

Kateryna Gotsulyak
Group: ІПЗм-26-1
Kharkiv National University of Radio Electronics
