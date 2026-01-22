#  Customer Query Solver Agent using RAG (Langflow + Astra DB)

This project implements a **Customer Query Solver Agent** using **Retrieval-Augmented Generation (RAG)** in **Langflow**.  
The system intelligently routes customer queries to specialized agents using a **Manager (Router) Agent**, ensuring accurate and context-aware responses.

---

##  Project Overview

The application is designed to handle different types of customer queries such as:

- **Frequently Asked Questions (FAQ)**
- **Order and Product-related Queries**

A **Manager Agent** analyzes the user query and dynamically decides which specialized agent (tool) should handle the request.

---

##  Architecture

```text
User Query
    ↓
Manager Agent (Router)
    ↓
--------------------------------
|                              |
FAQ Agent                 Order Lookup Agent
|                              |
FAQ Vector Store          Orders/Product Vector Store
(Astra DB)                (Astra DB)
|                              |
Gemini LLM (RAG-based Answer Generation)
