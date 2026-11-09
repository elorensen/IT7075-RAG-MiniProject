# LangChain RAG Mini Project

**IT7075: Applied AI for Cybersecurity — University of Cincinnati**

## Project Overview

This project rebuilds my original Retrieval-Augmented Generation (RAG) system using the LangChain framework. It uses the same five fictional cybersecurity SOC documents and eight evaluation questions as the original implementation. LangChain handles document loading, chunking, embeddings, vector storage, retrieval, and chain composition. The project compares LangChain against the original hand-built RAG implementation to evaluate retrieval performance, refusal behavior, and framework trade-offs.

## Implementation

The system uses the `all-MiniLM-L6-v2` local embedding model, Chroma vector storage, and LangChain's retrieval and prompt components. The graded retrieval evaluation runs on a CPU without an API key. In offline mode, the answer component displays retrieved evidence rather than generating a new LLM response.

## Evaluation Results

At the baseline configuration of 600-character chunks, 100-character overlap, four retrieved chunks, and a minimum relevance score of 0.25:

- Evidence found: **6/6 answerable questions**
- Refusals held: **1/2 unanswerable questions**

Both implementations produced identical retrieval and refusal measurements across seven tested configurations.

## Project Files

- `langchain_notebook.ipynb` — Completed notebook with saved outputs
- `my_kb/` — Five original cybersecurity knowledge-base documents
- `goldset.json` — Eight original evaluation questions
- `results_langchain.csv` — LangChain experiment results
- `ai_framework_kb.md` — Course practice knowledge base
- `framework_goldset.json` — Course practice questions
- `requirements.txt` — Python dependency versions

## Running the Notebook

1. Install Python 3.12 and create a virtual environment.
2. Install the packages using `pip install -r requirements.txt`.
3. Open `langchain_notebook.ipynb` in VS Code or Jupyter.
4. Select the Python environment containing the installed packages.
5. Run all cells from top to bottom.

The embedding model may need to download on the first run. No API key is required for offline evaluation.

## Limitations

The offline answer component previews retrieved evidence rather than generating a fully synthesized answer. Semantic similarity also does not guarantee factual answerability. Both implementations retrieved related documents for an unsupported security-awareness budget question, resulting in a failed refusal.