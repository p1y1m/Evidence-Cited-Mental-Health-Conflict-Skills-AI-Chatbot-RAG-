# Evidence-Cited-Mental-Health-Conflict-Skills-AI Agent-Chatbot-RAG

Author: Pedro Yanez Melendez

## What was built
- A scope-limited Q&A assistant that answers only about bullying, CBT emotion regulation, conflict resolution, negotiation, assertiveness, boundaries, and de-escalation.
- It retrieves evidence from reputable PDFs + web pages and cites sources in the answer.
- It refuses out-of-scope questions (example: cooking) to stay focused and safer.
- It showcases end-to-end LLM + Retrieval-Augmented Generation (RAG) skills in Colab.
- It produces helpful, practical, evidence-based guidance for common real-life conflict situations.

## How it works
- Download public PDFs (e.g., health services modules, anger management workbooks, bullying resources).
- Scrape selected public web pages into a JSONL knowledge file.
- Extract text from PDFs, split into chunks, and generate embeddings.
- Store embeddings in a FAISS vector index for fast retrieval.
- For each question: retrieve top passages, build a prompt, and generate a short answer (≤10 lines) with citations.

## Safety and scope rules
- Only answer within the approved topics listed above.
- If there is not enough evidence in the sources, say so and request a source to add.
- Keep responses practical, non-graphic, and appropriate for teens.

## Output and deliverables
- A working `ask()` function that returns:
  - Answer (max 10 lines)
  - Top 3 sources used
- An automated showcase pack:
  - Markdown report with 10 persona-based questions and cited answers
  - PPTX slides with the same Q&A for easy sharing

## Skills used
- Data ingestion (PDF + web), text cleaning, chunking, embeddings
- FAISS vector search, retrieval + prompt assembly
- Local open-source LLM inference in Colab
- Guardrails (topic gating + out-of-scope refusal)
- Automation: report + slides export

## Limitations
- The build can take time if too many documents are ingested in one run.
- Some websites block scraping (HTTP 403), so I used alternative sources or PDF copies.

## How it could be improved next
- Add true multimodal support (figures/tables/page images) and cite them.
- Keep a smaller curated library so the full run finishes in 10–20 minutes.
