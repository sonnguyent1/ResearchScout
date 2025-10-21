```markdown
# Personal Research Assistant (MVP)

Quick overview
- Ingest PDFs and markdown notes.
- Index using LlamaIndex and local vector store (Chroma/FAISS).
- Use a Hugging Face LLM (via Hub or Inference API) through LangChain for clarifying and summarizing.
- CLI to ask questions and export Markdown reports.

Setup
1. Create venv and activate:
   python -m venv .venv
   source .venv/bin/activate

2. Install requirements:
   pip install -r requirements.txt

3. Set Hugging Face token:
   export HUGGINGFACEHUB_API_TOKEN="hf_..."

4. Put a few PDFs or markdown files in examples/papers

Run
- Build index:
  python src/index/index_builder.py --data_dir examples/papers --index_path data/index

- Start CLI:
  python src/cli.py --index_path data/index

Files
- src/ingest/pdf_ingest.py: simple ingest utilities
- src/index/index_builder.py: builds LlamaIndex index
- src/agent/planner.py: simple ResearchPlanner that clarifies and synthesizes
- src/cli.py: interactive CLI
```