# Retrieval-Augmented Generation (RAG) Pipeline

This repository contains a complete implementation of a Retrieval-Augmented Generation (RAG) system, developed as part of an advanced NLP assignment. The project demonstrates how to ground large language model (LLM) responses in external knowledge to reduce hallucinations and improve factual accuracy.

## 📌 Overview

RAG combines **information retrieval** with **generative language models**. Given a user query, the system first retrieves relevant document chunks from a vector database, then uses them as context for an LLM to generate a grounded answer.

This notebook implements:

- Basic RAG pipeline
- RRR-RAG (Rewrite–Retrieve–Respond)
- Self‑RAG (iterative refinement)
- Web data ingestion (live article loading)
- Lexical vs. semantic retrieval comparison

## 🧠 Key Concepts Covered

| Concept | Description |
|---------|-------------|
| **Indexing** | Chunking documents and creating vector embeddings |
| **Retrieval** | Semantic search (dense embeddings) & lexical search (BM25) |
| **Augmentation** | Injecting retrieved context into the prompt |
| **Generation** | LLM producing the final answer using only the provided context |
| **RRR‑RAG** | Query rewriting before retrieval to improve relevance |
| **Self‑RAG** | Multiple retrieval–generation–refinement loops |

## 🛠️ Tech Stack

- **Language Models**: Groq (`llama-3.1-8b-instant`)
- **Embeddings**: `sentence-transformers/all-MiniLM-L6-v2` (HuggingFace)
- **Vector Store**: Chroma (local)
- **Text Splitting**: RecursiveCharacterTextSplitter (LangChain)
- **Web Loading**: WebBaseLoader + BeautifulSoup
- **Frameworks**: LangChain, LangChain Community

## Setup & Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/rag-assignment.git
   cd rag-assignment
2. Install dependencies
    ```
    pip install -q requests==2.32.4
    pip install -q langchain langchain-community chromadb sentence-transformers python-dotenv
    pip install -q groq langchain-groq beautifulsoup4
3. Set up Groq API key

      ```
      Get an API key from Groq Console
      Replace "Your_API_key" in the notebook cell:
      os.environ["GROQ_API_KEY"] = "your-key-here"
4. Run the notebook
     ```
     Open RAG_Assignment.ipynb in Jupyter/Colab/VSCode
     Execute cells sequentially
