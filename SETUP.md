# Setup & Configuration Guide

## Environment Setup Completed

This document records the setup work performed on the LEGAL-BUDDY project.

### Date: March 13, 2026

## Setup Steps Performed

### 1. Repository Setup
- ✅ Cloned the LEGAL-BUDDY repository from GitHub
- ✅ Navigated to project directory

### 2. Python Virtual Environment
- ✅ Created Python virtual environment (`.venv/`)
- ✅ Activated the virtual environment

### 3. Dependency Installation
- ✅ Installed all required packages from `requirements.txt`:
  - streamlit (1.55.0)
  - nest_asyncio (1.6.0)
  - pandas (2.3.3+)
  - langchain suite (langchain, langchain-classic, langchain-core, langchain-community)
  - langchain-google-genai (4.2.1)
  - langchain-groq (1.1.2)
  - langchain-text-splitters (1.1.1)
  - faiss-cpu (1.13.2)
  - pypdf (6.8.0)

### 4. Package Updates
- ✅ Upgraded all packages to their latest compatible versions
- Most packages were already at the latest versions
- Confirmed compatibility with Python 3.14

### 5. Environment Variables Configuration
Set the following environment variables (session-level):
```powershell
$env:GROQ_API_KEY="your-groq-api-key"
$env:GOOGLE_API_KEY="your-google-api-key"
```

### 6. Application Status
- ✅ All dependencies installed successfully
- ✅ Ready to run Streamlit application
- ✅ API keys configured for GROQ and Google services

## How to Run

1. **Activate Virtual Environment:**
   ```powershell
   .venv\Scripts\Activate.ps1
   ```

2. **Set API Keys:**
   ```powershell
   $env:GROQ_API_KEY="your-api-key"
   $env:GOOGLE_API_KEY="your-api-key"
   ```

3. **Start the Application:**
   ```powershell
   python -m streamlit run main.py
   ```

4. **Access the Application:**
   Open `http://localhost:8501` in your browser

## Key Components

- **GROQ_API_KEY**: Used for LLM inference (llama-3.1-8b-instant model)
- **GOOGLE_API_KEY**: Used for embeddings (gemini-embedding-001 model)
- **Streamlit**: Web interface framework
- **LangChain**: Framework for LLM applications with RAG
- **FAISS**: Vector store for semantic search
- **PyPDF**: PDF document processing

## Project Structure

```
LEGAL-BUDDY/
├── main.py                         # Main Streamlit application
├── requirements.txt                # Python dependencies
├── civil_law(RAG).json            # Legal knowledge base (civil law)
├── lawyer(RAG).json               # Legal knowledge base (lawyer info)
├── legal_contract_clauses.csv     # Contract clauses database
├── uploaded_docs/                 # Directory for user-uploaded documents
├── .venv/                         # Virtual environment (excluded from git)
└── README.md                      # Original project README
```

## Notes

- The `.venv/` directory is excluded from version control (see `.gitignore`)
- Environment variables should be set before running the application
- For production deployment, use Streamlit secrets management instead of environment variables
