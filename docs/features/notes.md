# AI Notes — Feature Documentation

> Turn raw lecture content into structured, study-ready material. **AI note taking for students**, with summarization, auto-tagging, and one-click conversion to quizzes or flashcards.

[← Back to README](../README.md) · [Architecture](../ARCHITECTURE.md)

![StudeQ AI Notes editor — AI lecture summarization and key concept detection for university students](../docs/screenshots/notes-feature.png)
*Lecture notes editor with live AI summary panel, concept tagging, and formula detection.*

---

## Overview

The **Notes** feature is StudeQ's AI-powered note taking and summarization tool. Students paste lecture text, type freehand, or upload a PDF — StudeQ condenses the content, auto-tags topics, highlights key concepts and formulas, and structures everything into a scannable summary. Notes are not siloed: every note feeds directly into the rest of the **AI study platform** — flashcards, quizzes, the study chat assistant, and the scheduler.

Route: `/features/notes`
Component: `client/src/pages/NotesFeaturePage.jsx`

## Features

| Feature | Description |
|---|---|
| **AI Summarization** | Condenses lecture content into scannable, exam-focused bullet points |
| **Smart Auto-Tagging** | Detects subject/topic and tags notes automatically — no manual filing |
| **Key Concept Detection** | Surfaces formulas, definitions, and critical dates at the top |
| **Multi-Format Input** | Accepts plain text, formatted notes, or PDF upload |
| **Notes → Quiz** | One-click conversion of any note into a multiple-choice or open-ended quiz |
| **Notes → Flashcards** | Generates a full flashcard deck from note content, spaced repetition enabled |

## How It Works

1. **Add Your Notes** — paste lecture text, type freehand, or upload a PDF
2. **AI Processes & Organizes** — summarizes, tags topics, highlights key concepts
3. **Study With Generated Material** — convert to quiz/flashcards, or review the structured summary

## Connected Features

Notes integrate directly with the rest of StudeQ's study ecosystem:

- **Flashcards** — deck built from note content
- **Quiz Engine** — questions generated from key concepts
- **AI Study Chat** — ask questions grounded in your own notes (RAG)
- **Scheduler** — auto-schedule review sessions for note content

## FAQ

<details>
<summary><strong>What types of notes does StudeQ support?</strong></summary>

Plain text, formatted lecture notes, and PDF uploads. Paste directly from your LMS, type freehand, or drop in a file — the AI processes any format without extra steps.
</details>

<details>
<summary><strong>How does AI summarization work?</strong></summary>

StudeQ analyzes note content using LLMs tuned for academic material, identifies key concepts, condenses lengthy explanations, and structures information into scannable summaries.
</details>

<details>
<summary><strong>Can I organize notes by subject or course?</strong></summary>

Yes. Notes are auto-tagged by detected subject area and can be manually assigned to courses. The dashboard groups by course.
</details>

<details>
<summary><strong>How accurate is the AI analysis?</strong></summary>

Accuracy scales with input quality — well-structured lecture content yields more precise summaries. AI output is always reviewable and editable before converting to flashcards or quizzes.
</details>

<details>
<summary><strong>Can I edit AI-generated summaries?</strong></summary>

Yes, all AI output is fully editable — treat it as a first draft.
</details>

<details>
<summary><strong>Is my note data private and secure?</strong></summary>

Notes are stored securely, never used to train models, and never shared with third parties. Each user's data is isolated.
</details>

## SEO / Metadata Implementation (current)

This page already implements:

- `react-helmet-async` for title, meta description, canonical, robots
- Open Graph + Twitter Card tags
- `SoftwareApplication`, `BreadcrumbList`, and `FAQPage` JSON-LD (`@graph`)
- Semantic landmarks (`<main>`, `aria-labelledby` sections, skip link)
- Accessible FAQ via `<dl>`/`<dt>`/`<dd>` + `aria-expanded`/`aria-controls`

---

**Related docs:** [README](../README.md) · [ARCHITECTURE](../ARCHITECTURE.md) · [CONTRIBUTING](../CONTRIBUTING.md)