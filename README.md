# 📄 RAG Pipeline for PDF Chat

A Streamlit web app that lets users **upload PDF documents** and **interactively ask questions** about their content using a **Retrieval-Augmented Generation (RAG)** pipeline.

---

## 🚀 Features

- Upload one or more PDF files
- Ask natural language questions about the uploaded PDFs
- Get accurate answers powered by a vector database + LLM
- Visualize and inspect the vector embeddings
- Download chat history for future reference

---

## 🧠 RAG Pipeline Overview

This app implements a classic **Retrieval-Augmented Generation (RAG)** pipeline:

```
PDF(s) → Chunking → Embedding → Vector Store → Retrieval → LLM (Answering)
```

### 🔹 Step-by-step:

1. **PDF Upload**  
   PDFs are uploaded by the user and temporarily saved.

2. **Chunking & Embedding**  
   The PDF content is split into chunks and transformed into **dense vector embeddings** using a pre-trained embedding model.

3. **Vector Store (ChromaDB)**  
   All embeddings are stored in a **ChromaDB** vector database for fast similarity search.

4. **Query Input**  
   The user enters a question in natural language via the Streamlit interface.

5. **Retriever**  
   The top relevant chunks from the vector store are retrieved based on cosine similarity to the user’s query.

6. **LLM (Answer Generator)**  
   The retrieved context + question is passed to an LLM (e.g., OpenAI or HuggingFace model) to generate a final answer.

---

## 📁 Project Structure

```
RAG-PDF-Chat/
│
├── app.py                         # Main Streamlit app
├── requirements.txt              # Python dependencies
├── utils/
│   ├── __init__.py
│   ├── pdf_handler.py            # Handles PDF upload and chunking
│   ├── store_vector.py           # Embedding and vectorstore loading
│   ├── llm.py                    # Loads LLM chain for answering
│   ├── chat.py                   # Manages chat history and input
│   └── chroma_inspector.py       # Optional ChromaDB viewer
```

---

## 🛠️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/rag-pdf-chat.git
cd rag-pdf-chat
```

### 2. (Optional) Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🧪 Run the App

```bash
streamlit run app.py
```

After launching, the app will open in your browser.
