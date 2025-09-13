# RAG LangChain Chroma Groq

A simple Retrieval-Augmented Generation (RAG) question-answering application using **LangChain**, **ChromaDB**, **Groq LLM**, and **local sentence-transformer embeddings**.

## Overview

This project demonstrates how to build an end-to-end RAG pipeline:
- **Document ingestion & chunking** – loads a folder of text documents and splits them into manageable chunks.
- **Local embeddings** – uses the `sentence-transformers/all-MiniLM-L6-v2` model to create vector representations of each chunk.
- **Vector database** – stores embeddings in a persistent **Chroma** database for fast semantic search.
- **LLM response generation** – retrieves the most relevant chunks and passes them to a **Groq LLM** (e.g., `mixtral-8x7b-32768`) to generate accurate answers to natural-language questions.

This setup is useful for building custom knowledge assistants, documentation search tools, or any system where private or curated data must be combined with LLM reasoning.

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Abuaisha-7/chroma-rag-qa.git
   cd chroma-rag-qa

2. **Create a virtual environment and install dependencies**
   ```bash
   python -m venv venv
   source venv/bin/activate   # or venv\\Scripts\\activate on Windows
   pip install -r requirements.txt

   Key packages: langchain, chromadb, groq, sentence-transformers, tiktoken.

3. **Set your Groq API key**
    ```bash
    export GROQ_API_KEY="your_groq_api_key"

## Usage

1. **Prepare documents**
   Place .txt files (e.g., Wikipedia articles, open-access papers) in the data/ directory.

2. **Run the application**
   ```bash
   python qa_vector_db_ingest.py
   python qa_vector_db_rag.py

3. **Ask questions**
   Type a question at the prompt and get an AI-generated answer based on your documents.

## License
   
   This project is released under the MIT License. See the LICENSE
   file for details.