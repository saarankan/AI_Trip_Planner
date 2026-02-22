# RAG Chatbot (Streamlit + LangGraph + Chroma)

A simple Retrieval-Augmented Generation (RAG) chatbot that:
- ingests knowledge from a web page and local PDFs,
- stores embeddings in ChromaDB,
- answers questions in a Streamlit chat UI using Groq (`llama-3.1-8b-instant`).

## Features

- **Document ingestion pipeline** in `ingest.py`
  - Loads content from a configured website (`WEB_URL`)
  - Loads PDF files from `data/pdfs`
  - Splits text into chunks
  - Creates embeddings with `intfloat/multilingual-e5-large`
  - Persists vectors to `docs/chroma`
- **Chat app** in `app.py`
  - Retrieves top-k relevant chunks from ChromaDB
  - Uses LangGraph + ChatGroq for response generation
  - Shows source document and reference page numbers

## Project Structure

```text
RAG/
├─ app.py
├─ ingest.py
├─ config.py
├─ requirements.txt
├─ .env
├─ data/
│  ├─ Docs/
│  └─ pdfs/
└─ docs/
   └─ chroma/
```

## Requirements

- Python 3.10+
- A Groq API key

## Setup

1. **Create and activate virtual environment**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2. **Install dependencies**

```powershell
pip install -r requirements.txt
```

3. **Create `.env` file**

```env
GROQ_API_KEY=your_groq_api_key_here
```
