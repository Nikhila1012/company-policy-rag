# Company Policy RAG

A Retrieval-Augmented Generation (RAG) system that answers questions from a company employee policy document.

## Project Overview

This project uses RAG to retrieve relevant information from a company policy PDF and generate answers to user questions based only on the retrieved policy content.

The system follows this pipeline:

PDF → Text Chunks → Embeddings → FAISS Vector Database → Retriever → LLM → Answer

## Technologies Used

- Python
- LangChain
- Hugging Face Transformers
- FAISS
- Sentence Transformers
- Google Colab

## Models and Configuration

### Document Embeddings
- Model: `BAAI/bge-small-en-v1.5`

### Vector Database
- FAISS

### Language Model
- Model: `HuggingFaceTB/SmolLM2-1.7B-Instruct`

### RAG Configuration
- Chunk size: 700
- Chunk overlap: 100
- Top K documents: 4
- Temperature: 0.2
- Maximum new tokens: 100

## How It Works

1. The company policy PDF is loaded using `PyPDFLoader`.
2. The document is divided into smaller chunks.
3. Each chunk is converted into an embedding using BGE.
4. The embeddings are stored in a FAISS vector database.
5. When a user asks a question, the most relevant chunks are retrieved.
6. The retrieved context is passed to the language model.
7. The language model generates an answer based on the retrieved policy information.

## Example Questions

- What are the standard working hours?
- How many casual leave days are employees entitled to?
- What is the company's remote work policy?
- What are the rules regarding employee benefits?

## Project Files

```text
company-policy-rag/
│
├── Company_policy_RAG.ipynb
├── AcmeTech_Employee_Policy_Manual.pdf
└── README.md
