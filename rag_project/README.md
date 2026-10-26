
# Cybersecurity SOC Retrieval-Augmented Generation System

This project was developed for IT7075: Applied AI for Cybersecurity at the University of Cincinnati.

## Project Overview

This notebook implements a Retrieval-Augmented Generation (RAG) system using five original, fictional cybersecurity operations documents covering phishing triage, email authentication, incident response, malware analysis, and security awareness.

The system chunks documents into overlapping passages, generates embeddings using the all-MiniLM-L6-v2 sentence transformer, stores them in ChromaDB, and retrieves relevant passages to support grounded responses.

## Evaluation

The custom gold set contains eight questions: six answerable and two unanswerable.

The baseline configuration uses:
- Chunk size: 600 characters
- Overlap: 100 characters
- Retrieved chunks: 4
- Maximum cosine distance: 0.75

Baseline results:
- Evidence found: 6/6
- Refusals held: 1/2

Seven configurations were evaluated. Results are saved in `results.csv`, and the comparison chart is saved as `figure.png`.

## Running the Project

1. Install Python 3.12.
2. Install the required packages:
   `pip install sentence-transformers chromadb pandas matplotlib ipykernel`
3. Open `rag_notebook.ipynb` in Jupyter or VS Code.
4. Select a Python kernel with the required packages.
5. Run the notebook from top to bottom.

The notebook works offline after its embedding model has been downloaded. Its offline answer mode displays retrieved evidence rather than generating a fully synthesized LLM response.

## Files

- `rag_notebook.ipynb` — Completed RAG implementation, evaluation, and saved outputs.
- `goldset.json` — Eight custom evaluation questions.
- `results.csv` — Experiment results.
- `figure.png` — Experiment chart.
- `my_kb/` — Five knowledge-base documents and source documentation.
- `baseline_goldset.json`, `ssrf.txt`, `cybersecurity_kb.md` — Course practice data.

## Limitations

The system uses semantic similarity to retrieve evidence. Related passages may not contain the precise information requested. The annual security-awareness budget question demonstrated this limitation.

This is an educational prototype using fictional data, not a production SOC system.