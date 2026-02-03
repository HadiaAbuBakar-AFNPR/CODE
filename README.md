# NKG-RAG: Retrieval-Augmented News Knowledge Graph Construction

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)

**Reduces LLM hallucinations via NewsOnt + LlamaIndex/Neo4j RAG pipeline.** Builds KG triples (Person-InvolvedIn-Event) from news articles with source attribution.

## 🎯 Features
- Custom OWL NewsOnt (events, places, temporal relations)
- End-to-end: Text → Embeddings → Retrieve → LLM KG generation → Neo4j storage
- Hallucination mitigation: RAG top-k=5 chunks
- Reproducible: Runs on CPU/GPU, ~2min/article

## 📋 Prerequisites
- Python 3.10+
- Neo4j Desktop (free): Download [here](https://neo4j.com/download/)
- OpenAI API key (or local LLM)

## 🚀 Quick Start (5 mins)
```bash
# 1. Clone & install
git clone https://github.com/HadiaAbuBakar-AFNPR/CODE.git
cd CODE
pip install -r requirements.txt

# 2. Setup Neo4j (bolt://localhost:7687, user:neo4j, pass:yourpass)
# Start Neo4j Desktop > New DBMS > Set password

# 3. Add your OpenAI key
export OPENAI_API_KEY="sk-..."

# 4. Run pipeline
python nkg_rag_pipeline.py --news_file samples/sample_news.txt --neo_uri bolt://localhost:7687 --neo_user neo4j --neo_pass yourpass
**Output**: Neo4j KG populated; `output/kg.html` visualized.

## 📁 Repo Structure

