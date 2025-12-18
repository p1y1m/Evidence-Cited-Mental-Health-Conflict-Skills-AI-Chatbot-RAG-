# Bullying + CBT + Conflict Skills AI Chatbot (RAG, Google Colab)

Author: Pedro Yáñez Meléndez

## What I built
- An AI Q&A chatbot focused on bullying response skills, CBT-based emotion regulation, conflict resolution, negotiation, assertiveness, boundaries, and de-escalation.
- It uses Retrieval-Augmented Generation (RAG): it retrieves relevant passages from reputable PDFs and selected web pages, then generates a short answer with citations.
- It supports persona-aware questions (age + role) so answers fit the situation.

## Why I built it
- To showcase end-to-end AI engineering in Google Colab using only open-source models and public sources.
- To produce practical, evidence-cited guidance people can use in real conversations.

## How it works
- Collect public PDFs (CBT modules, coping skills, anger management, bullying resources).
- Collect selected public web pages and store them as text records.
- Extract text, split into chunks, and generate embeddings.
- Store embeddings in a FAISS vector index for fast retrieval.
- For each question: retrieve top passages, assemble a prompt, and generate an answer (≤10 lines) plus the top 3 sources.

## Output and deliverables
- A working `ask()` pipeline that returns:
  - Answer (max 10 lines)
  - Top 3 sources used
- A simple web UI (Gradio) to test the chatbot interactively.
- An export pack:
  - Markdown report with persona-based questions and cited answers
  - PPTX slides with the same Q&A for easy sharing

## Skills demonstrated
- Data ingestion (PDF + web), text cleaning, chunking, embeddings
- FAISS vector search, retrieval + prompt assembly
- Local open-source LLM inference in Colab (no paid API)
- Prompting for concise, source-cited answers
- Automation: report + slides export

## Limitations
- Ingesting many documents increases build time and RAM usage.
- Some sites block scraping (HTTP 403), so alternative mirrors or PDF copies may be needed.

## How I would improve it next
- Add true multimodal ingestion (figures/tables/page images) with citations.
- Keep a smaller curated library so the full run finishes faster while staying high quality.
