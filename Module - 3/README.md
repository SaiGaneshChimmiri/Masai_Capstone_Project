# Zepto Data & AI Platform

A complete data and AI platform project built with Python, Pandas, Scikit-learn, SQLite, ChromaDB, FastAPI, and LangChain.

The project contains three major modules:

1. Data Pipeline
2. Analytics & Machine Learning
3. AI-Powered Support Assistant

---

## Project Overview

The Zepto Data & AI Platform demonstrates an end-to-end workflow starting from data collection and cleaning, followed by analytics and machine learning, and finally an AI-powered support assistant.

### Main Workflow

Data Collection
        ↓
Data Cleaning & Transformation
        ↓
SQLite Database + CSV
        ↓
Exploratory Data Analysis
        ↓
Machine Learning Models
        ↓
Policy Documents
        ↓
Vector Database
        ↓
AI Support Assistant
        ↓
FastAPI REST API

---

# Technologies Used

## Programming Language

- Python

## Data Engineering

- Requests
- BeautifulSoup
- Pandas
- SQLite

## Data Analysis

- Pandas
- NumPy
- Matplotlib
- Seaborn

## Machine Learning

- Scikit-learn
- Logistic Regression
- Decision Tree
- Random Forest
- GridSearchCV

## AI / NLP

- LangChain
- ChromaDB
- Retrieval-Augmented Generation (RAG)

## Backend

- FastAPI
- Uvicorn
- Pydantic

## Development Tools

- VS Code
- Git
- GitHub

---

# Project Structure

```text
zepto_data_ai_platform/
│
├── analytics/
│   ├── outputs/
│   ├── 01_eda.py
│   ├── 02_modeling.py
│   ├── README.md
│   └── titanic.csv
│
├── data_pipeline/
│   └── pipeline.py
│
├── support_assistant/
│   ├── chroma_db/
│   ├── data/
│   ├── docs/
│   ├── __init__.py
│   ├── build_index.py
│   ├── demo_calls.py
│   ├── Dockerfile
│   ├── main.py
│   ├── prompt.py
│   └── README.md
│
├── .gitignore
├── feature_notes.md
├── README.md
└── requirements.txt
