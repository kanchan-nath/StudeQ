# AI Quiz Maker — Feature Documentation

> Generate MCQ, true/false, fill-in-the-blank, and short-answer **quizzes from your notes** or any topic in seconds. **AI quiz maker** with adaptive difficulty and instant explanations — built for **exam prep**.

[← Back to README](../README.md) · [Architecture](../ARCHITECTURE.md) · [Notes Feature](notes.md)

![StudeQ AI quiz maker — generate quizzes from notes, PDFs, or topics with adaptive difficulty](../docs/screenshots/quiz-feature.png)
*Quiz generation screen showing MCQ output with answer keys and explanations.*

---

## Overview

The **Quiz** feature is StudeQ's AI-powered quiz generation engine. Students upload notes, paste a topic, or drop a PDF — StudeQ generates a structured quiz with answer keys and explanations in under 10 seconds. Questions are grounded in the student's actual material (context-aware generation), not generic trivia, and difficulty adapts based on performance.

Route: `/features/quiz`
Component: `client/src/pages/QuizFeaturePage.jsx`

## Question Types

| Type | Description |
|---|---|
| **Multiple Choice** | Classic 4-option questions auto-generated from any topic or uploaded notes |
| **True / False** | Rapid-fire binary questions for fact retention and quick review |
| **Short Answer** | Open-ended questions, graded by AI for semantic accuracy (not exact match) |
| **Fill in the Blank** | Cloze-style questions pulled directly from study material |
| **Flashcard Drill** | Spaced-repetition flashcards with difficulty ratings and auto-scheduling |
| **Concept Explain** | AI asks the student to explain a concept, grades for depth and accuracy |

## How It Works

1. **Upload or Paste** — notes, PDFs, URLs, or just a topic name
2. **Configure Quiz** — pick question types, count, difficulty, time limit
3. **Generate in Seconds** — AI produces a full structured quiz with answer keys
4. **Take & Track** — instant feedback, weak spots surfaced automatically

## Feature Deep Dive

| Feature | Description |
|---|---|
| **Context-Aware Generation** | Questions grounded in actual uploaded material — no hallucinated facts |
| **Performance Analytics** | Per-question accuracy, time spent, repeated mistakes, mastery score per concept |
| **Adaptive Difficulty** | Increases difficulty on weak question types, backs off on mastered topics |
| **Detailed Explanations** | Source-cited explanation per answer, plus rationale for why other options are wrong |
| **Quiz History & Retake** | Every quiz saved — retake, regenerate variants, or export as PDF |
| **Share & Compete** | Publish a quiz link, friends attempt it, scores compare on a leaderboard |

## Input Sources

StudeQ ingests material as-is, no reformatting required:

- PDF lecture notes or textbook chapters
- Pasted raw text or bullet points
- Article or Wikipedia URL
- Lecture transcript (auto or manual)
- Just a topic name — AI fills the rest

## SEO / Metadata Implementation (current)

This page already implements:

- `react-helmet-async` for title, meta description, canonical, robots
- Open Graph + Twitter Card tags
- `SoftwareApplication` JSON-LD with `featureList`
- Tab-pattern question type explorer with proper `role="tablist"`/`role="tab"`/`role="tabpanel"` + `aria-selected`/`aria-controls`
- Semantic landmarks (`<main>`, `aria-labelledby` sections, skip link)

---

**Related docs:** [README](../README.md) · [ARCHITECTURE](../ARCHITECTURE.md) · [Notes Feature](notes.md) · [CONTRIBUTING](../CONTRIBUTING.md)