# AI Notebook — Feature Documentation

> Upload PDFs, research papers, or lecture slides and have **AI-powered, citation-grounded conversations** with your own sources. A **RAG study assistant** built for students — like NotebookLM, with page-level citations and zero hallucinations.

[← Back to README](../README.md) · [Architecture](../ARCHITECTURE.md) · [Notes](notes.md) · [Quiz](quiz.md) · [Flashcards](flashcard.md)

![StudeQ AI notebook — chat with your uploaded documents with page-level citations](../docs/screenshots/notebook-feature.png)
*Notebook chat interface showing source-grounded answers with inline citations.*

---

## Overview

The **Notebook** feature is StudeQ's document-grounded AI chat — upload PDFs, Word docs, slides, or pasted text, and ask questions in plain language. Every answer is cited back to an exact page, paragraph, or slide in the source material, with no external/internet data used. This is the clearest expression of StudeQ's **RAG study assistant** architecture (Pinecone retrieval + multi-LLM generation) at the feature level.

Route: `/features/notebook`
Component: `client/src/pages/NotebookFeaturePage.jsx`

## Capabilities

| Capability | Description |
|---|---|
| **Ask Anything** | Plain-language questions answered with exact page-level citations from uploaded sources only |
| **Summarize Docs** | Structured summary of any document — key arguments, methodology, conclusions, open questions |
| **Compare Sources** | Upload multiple papers/chapters, compare theories, find contradictions, synthesize a unified view |
| **Explain Concepts** | Highlight a passage, ask AI to simplify, elaborate, or connect it to other notebook content |
| **Generate Outlines** | Turn a document or discussion into an essay outline, study guide, or presentation skeleton |
| **Auto-Citations** | Every answer links to exact source locations; export in APA, MLA, or Chicago format |

## How It Works

1. **Create a Notebook** — name by topic, course, or project; each notebook is an isolated knowledge space
2. **Upload Your Sources** — PDFs, Word docs, slides, or pasted text — all parsed and indexed
3. **Start the Conversation** — threaded chat grounded in uploaded documents
4. **Export & Share** — export conversation/notes/citations as PDF or shareable link, collaborate in real time

## Source-Grounded Answers

Unlike generic AI chatbots, Notebook answers **only** from what was uploaded:

- Page-level source pins on every answer
- No internet data — only your documents
- Export citations in APA, MLA, or Chicago format
- Click any citation to jump to the source passage

## Use Cases

| Use Case | Example |
|---|---|
| **Research Papers** | Upload 10 papers, ask "what do they agree and disagree on?" — synthesis in under 30 seconds |
| **Textbook Study** | Upload chapters, get concept explanations and practice questions from the same notebook |
| **Case Analysis** | Upload legal, business, or medical case documents and interrogate them like an expert |
| **Lab Reports & Data** | Upload experimental data and prior studies, ask AI to spot patterns and anomalies |

## Supported Sources

- PDF — research papers, textbooks, reports
- Word Docs — essays, drafts, case notes
- Slide Decks — lecture PPTs and keynotes
- Pasted Text — raw notes or copied passages
- URLs — articles, Wikipedia, blog posts
- Transcripts — lecture recordings or interviews

## SEO / Metadata Implementation (current)

This page already implements:

- `react-helmet-async` for title, meta description, canonical, robots
- Open Graph + Twitter Card tags
- `SoftwareApplication` JSON-LD with detailed `featureList`
- Capability explorer using the same tab pattern as quiz.md/flashcard.md (`role="tablist"`/`"tab"`/`"tabpanel"`)
- Semantic landmarks (`<main>`, `aria-labelledby` sections, skip link)
---

**Related docs:** [README](../README.md) · [ARCHITECTURE](../ARCHITECTURE.md) · [Notes](notes.md) · [Quiz](quiz.md) · [Flashcards](flashcard.md) · [CONTRIBUTING](../CONTRIBUTING.md)