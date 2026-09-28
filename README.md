# Masai_Capstone_Project
# Zepto Support Assistant — Module 3 Assessment

A complete, production-ready GenAI support assistant service for **Zepto** built with **ChromaDB**, **LangGraph**, **FastAPI**, and **Pydantic**. 

This repository contains:
1. A **local document corpus** and vector pipeline built with `sentence-transformers/all-MiniLM-L6-v2` and **ChromaDB**.
2. A **LangGraph orchestrated workflow** with intent classification routing and grounded context retrieval.
3. A **deterministic offline mock mode (`MOCK_LLM=1`)** as the primary graded baseline (no API keys or network access required).
4. An **optional Groq API extension (`MOCK_LLM=0`)** with automatic Pydantic schema validation retries.
5. A **FastAPI service** exposing a `/ask` endpoint.
6. A **Dockerfile** for local containerization and optional deployment.

---

## 🏗️ Pipeline Architecture

```text
                  ┌──────────────────────┐
                  │      User Query      │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │   classify_intent    │
                  └──────────┬───────────┘
                             │
             ┌───────────────┴───────────────┐
             │                               │
    (policy_question)                (general_question)
             │                               │
             ▼                               ▼
  ┌──────────────────────┐        ┌──────────────────────┐
  │ retrieve_and_answer  │        │    direct_answer     │
  └──────────┬───────────┘        └──────────┬───────────┘
             │                               │
      [ChromaDB Vector]                      │
             │                               │
             └───────────────┬───────────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Pydantic Validation  │
                  │ (answer/sources/conf)│
                  └──────────────────────┘
