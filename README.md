# RAG-PIPELINE
#  RAG Pipeline with Mistral

This project demonstrates a **Retrieval-Augmented Generation (RAG)** system built in Google Colab using the **Mistral language model**. It is designed to answer questions about legal texts using only the information explicitly provided in the source documents.

---

##  Objective

The goal is to evaluate whether a language model (Mistral) can generate accurate and legally grounded answers **only using retrieved context** from a legal document — specifically, the **EU Artificial Intelligence Act**.

---

##  Task Overview

1. **Document Source**: A legal PDF file containing the EU AI Act.
2. **Chunking and Embedding**: The document is split into text chunks and embedded using Sentence Transformers.
3. **Vector Store**: Chunks are stored in a FAISS index for efficient retrieval.
4. **User Query**: A legal question is provided.
5. **Context Retrieval**: Top matching chunks are retrieved based on the query.
6. **Generation**: The Mistral model answers the question using the retrieved context only.
7. **Evaluation**: The output is checked to ensure it strictly uses the legal context and adheres to the format provided in the task description.

---

##  Evaluation Criteria

- The answer **must only use** content from the provided context
- **No external knowledge** or assumptions should be introduced
- Legal citations such as `(see Article X)` or `(see [Page X])` should be preserved if they appear in the context
- If the context does not include an answer, the model should reply with:
  > "The context does not provide a complete answer to this question."

---

## 🔧 Requirements

Install the following dependencies using:

```bash
pip install -r requirements.txt
