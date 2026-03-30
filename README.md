# 🤖 Multi-PDF ChatApp AI Agent

A sophisticated **Retrieval-Augmented Generation (RAG)** application that transforms static PDF documents into an interactive, conversational knowledge base. By leveraging **Google Gemini Pro** and **FAISS**, this agent allows users to "chat" with multiple complex documents simultaneously, receiving answers grounded strictly in the provided text.

---

## 🚀 Overview

Traditional LLMs often hallucinate or lack access to private, niche data. This project solves that by implementing a custom RAG pipeline. It extracts, processes, and indexes text from multiple PDFs, allowing for high-accuracy information retrieval.

### **Key Features**
* **Multi-Document Context:** Analyze and cross-reference information across several PDFs in a single session.
* **Semantic Search:** Uses vector embeddings to understand the *meaning* of your query, not just keyword matching.
* **Conversational Memory:** Maintains chat history for context-aware follow-up questions.
* **Streamlit Interface:** A clean, user-friendly web UI for seamless file uploads and interaction.

---

## 🛠️ Tech Stack

| Component | Technology |
| :--- | :--- |
| **LLM** | Google Gemini Pro |
| **Orchestration** | LangChain |
| **Vector Database** | FAISS (Facebook AI Similarity Search) |
| **Language** | Python / TypeScript |
| **Interface** | Streamlit |
| **PDF Parsing** | PyPDF2 |

---

## 🧠 How It Works: The RAG Pipeline

The application follows a four-stage process to ensure accurate responses:

1.  **Text Extraction:** Raw text is pulled from uploaded PDFs page-by-page.
2.  **Chunking:** The text is broken into smaller, overlapping segments (e.g., 1000 characters with a 200-character overlap) to preserve context and stay within LLM token limits.
3.  **Vectorization:** Each chunk is converted into a high-dimensional vector embedding using Google's Generative AI models.
4.  **Vector Storage (FAISS):** These embeddings are stored in a local **FAISS** index. When a user asks a question, the app performs a similarity search to find the most relevant chunks to feed the LLM.
