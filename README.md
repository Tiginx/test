# 🔍 RAG Database Project

A Retrieval-Augmented Generation (RAG) system built with Python. This project enables intelligent document retrieval combined with LLM-powered answer generation.

---

## 📌 Overview

RAG (Retrieval-Augmented Generation) enhances large language models by grounding their responses in a custom knowledge base. Instead of relying solely on pre-trained knowledge, the model retrieves relevant documents from a vector database and uses them as context when generating answers.

---

## 🗂️ Project Structure

```
rag-database/
├── data/                  # Raw documents and datasets
├── embeddings/            # Stored vector embeddings
├── src/
│   ├── ingest.py          # Document loading & chunking
│   ├── embed.py           # Embedding generation
│   ├── retriever.py       # Vector search & retrieval
│   ├── generator.py       # LLM answer generation
│   └── pipeline.py        # End-to-end RAG pipeline
├── tests/                 # Unit tests
├── requirements.txt       # Python dependencies
├── .env.example           # Example environment variables
└── main.py                # Entry point
```

---

## ⚙️ Tech Stack

| Component        | Technology                        |
|------------------|-----------------------------------|
| Language         | Python 3.10+                      |
| Vector Database  | ChromaDB / FAISS                  |
| Embeddings       | OpenAI `text-embedding-ada-002` / HuggingFace |
| LLM              | OpenAI GPT / Ollama (local)       |
| Document Loader  | LangChain / LlamaIndex            |
| Environment      | `python-dotenv`                   |

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Tiginx/test.git
cd test
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

```bash
cp .env.example .env
# Edit .env and add your API keys
```

### 5. Ingest documents

```bash
python src/ingest.py --source ./data
```

### 6. Run the RAG pipeline

```bash
python main.py
```

---

## 🧠 How It Works

1. **Ingestion** — Documents are loaded, split into chunks, and stored
2. **Embedding** — Each chunk is converted into a vector using an embedding model
3. **Indexing** — Vectors are stored in a vector database (ChromaDB/FAISS)
4. **Retrieval** — On query, the top-k most similar chunks are fetched
5. **Generation** — The retrieved context is passed to an LLM to generate an answer

```
User Query → Embed Query → Vector Search → Retrieve Chunks → LLM → Answer
```

---

## 🔑 Environment Variables

```env
OPENAI_API_KEY=your_openai_api_key
EMBEDDING_MODEL=text-embedding-ada-002
LLM_MODEL=gpt-4o
VECTOR_DB_PATH=./embeddings
CHUNK_SIZE=512
CHUNK_OVERLAP=50
TOP_K=5
```

---

## 📦 Requirements

```
langchain
chromadb
openai
python-dotenv
tiktoken
faiss-cpu
sentence-transformers
```

---

## 🤝 Contributing

Pull requests are welcome! Please open an issue first to discuss what you'd like to change.

---

## 📄 License

MIT License — feel free to use and modify.
