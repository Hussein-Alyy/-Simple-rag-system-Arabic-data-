# 🔎 RAG Implementations Comparison (Cosine vs FAISS)

This project demonstrates multiple implementations of **Retrieval-Augmented Generation (RAG)** using:

* 🧠 Gemini LLM
* 🔤 Sentence Transformers (`BAAI/bge-m3`)
* 📊 Cosine Similarity
* ⚡ FAISS Vector Database

The goal is to compare different retrieval strategies while keeping the same generative model.

---

## 📌 Project Objective

To implement the same RAG pipeline using:

1. **Manual similarity search (NumPy + Cosine)**
2. **FAISS-based vector indexing**

Both approaches:

* Retrieve relevant context
* Inject it into a prompt
* Use Gemini to generate the final answer

---

## 🏗️ Architecture Overview

### 🟢 Version 1 – Cosine Similarity (In-Memory)

```text
Document → Chunking → Embedding → Cosine Similarity → Top-K → LLM → Answer
```

* Stores embeddings in memory
* Uses `sklearn.metrics.pairwise.cosine_similarity`
* Simple and lightweight
* Good for small datasets

---

### 🔵 Version 2 – FAISS-Based Retrieval

```text
Document → Chunking → Embedding → FAISS Index → Top-K Search → LLM → Answer
```

* Uses FAISS for fast similarity search
* Supports scalable vector indexing
* Saves index to disk
* Suitable for larger knowledge bases

---

## 🛠️ Technologies Used

* Python
* Google Gemini (`gemini-2.5-flash`)
* SentenceTransformers (`BAAI/bge-m3`)
* NumPy
* Scikit-learn
* FAISS
* HuggingFace Hub

---

## 📂 Workflow Steps

### 1️⃣ Document Processing

* Load text file
* Split into chunks
* Clean empty segments

### 2️⃣ Embedding Generation

* Convert text into dense vectors
* Use multilingual embedding model

### 3️⃣ Retrieval

#### Cosine Version:

* Compute similarity matrix
* Sort scores
* Select Top-K chunks

#### FAISS Version:

* Build vector index
* Perform fast nearest neighbor search
* Retrieve Top-K results

### 4️⃣ Generation

* Inject retrieved context into structured prompt
* Force answer based only on context
* Gemini generates final response

---

## 📊 Comparison Between Approaches

| Feature          | Cosine Similarity | FAISS     |
| ---------------- | ----------------- | --------- |
| Speed            | Medium            | Very Fast |
| Scalability      | Limited           | High      |
| Persistence      | No                | Yes       |
| Production Ready | Basic             | Yes       |
| Complexity       | Simple            | Advanced  |

---

## 🎯 Key Highlights

* Same LLM used in both versions
* Same embedding model
* Different retrieval engines
* Demonstrates impact of vector database
* Shows understanding of RAG architecture

---

## 🧠 Why This Matters

This project proves:

* Understanding of retrieval systems
* Knowledge of vector databases
* Practical implementation of RAG
* Ability to compare architectural choices
* Production-level thinking

---

## 🚀 Future Improvements

* Add hybrid search (BM25 + Embeddings)
* Add reranking model
* Use chunk overlap strategy
* Add metadata filtering
* Deploy as API service
* Integrate with Streamlit UI
* Add evaluation metrics (Recall@K, MRR)

---

## 📌 Project Value

This repository demonstrates:

* Advanced RAG engineering
* Vector database integration
* LLM prompt control
* Scalable AI architecture design
* Real-world knowledge grounding
