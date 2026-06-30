# AI Flashcard Maker — Feature Documentation

> Generate smart **flashcard decks** from any notes or PDF. Six study modes, **spaced repetition** (SM-2), and AI-powered mastery tracking — an **AI flashcards generator** built for exam prep, not just card storage.

[← Back to README](../README.md) · [Architecture](../ARCHITECTURE.md) · [Notes Feature](notes.md) · [Quiz Feature](quiz.md)

![StudeQ AI flashcard maker — spaced repetition flashcards generated from notes and PDFs](../docs/screenshots/flashcard-feature.png)
*Flashcard deck view with spaced repetition schedule and study mode tabs.*

---

## Overview

The **Flashcards** feature is StudeQ's AI-powered flashcard generation and spaced-repetition study engine. Students upload notes, paste a topic, or drop a PDF — StudeQ extracts key terms and concepts and produces a full deck in under 10 seconds. Cards are then scheduled using the **SM-2 algorithm** (the same engine behind Anki), resurfacing each card right before the student is about to forget it.

Route: `/features/flashcards`
Component: `client/src/pages/FlashcardFeaturePage.jsx`

## Study Modes

| Mode | Description |
|---|---|
| **Classic Flip** | Tap to reveal the answer, self-rate Got it / Almost / Missed — reschedules accordingly |
| **Spaced Repetition** | SM-2 algorithm surfaces cards at optimal intervals |
| **Type the Answer** | AI grades typed responses semantically, partial credit for correct concepts |
| **Quiz Mode** | Each card becomes a 4-option MCQ; distractors generated from related cards in the deck |
| **Match Game** | Drag terms to definitions under a timer — vocabulary/formula drilling |
| **Speak the Answer** | Voice input, AI transcribes and grades — hands-free study |

## How It Works

1. **Pick a Source** — upload notes, paste text, enter a topic, or link a URL
2. **AI Generates Cards** — extracts key terms, concepts, and relationships into a full deck in under 10 seconds
3. **Review & Customize** — edit, delete, add cards; merge sources; tag and organize by topic
4. **Study & Track Progress** — pick a study mode, watch mastery scores rise, weak cards resurface automatically

## Spaced Repetition (SM-2)

StudeQ uses the **SM-2 algorithm** — same engine behind Anki — to schedule each card at the moment a student is about to forget it:

- Review only cards about to be forgotten — zero wasted sessions
- Each correct answer pushes the next review further out
- Missed cards return the next day; mastered cards return in weeks
- Deck mastery score tracks real retention, not just attempt count

## Feature Deep Dive

| Feature | Description |
|---|---|
| **Concept-Level Generation** | AI identifies actual testable concepts, not just lifted sentences |
| **Mastery Dashboard** | Per-card accuracy, streak, last reviewed date, deck-level mastery % |
| **Smart Resurfacing** | Struggling cards return sooner/more often; mastered cards back off for days — zero manual scheduling |
| **AI Card Editor** | Rewrite a card simpler, add an example, split into two cards, or generate a mnemonic |
| **Deck Merging & Tagging** | Merge decks from different notebooks, tag by exam/topic, filter review sessions |
| **Export & Share** | CSV, Anki-compatible APKG, or shareable link |

## Export & Compatibility

- Export as **Anki APKG** — full compatibility, no lock-in
- Export as **CSV** — open in any spreadsheet
- **Share deck link** — anyone can study or fork it, no account needed
- Export as **printable PDF** flashcard sheets

## SEO / Metadata Implementation (current)

This page already implements:

- `react-helmet-async` for title, meta description, canonical, robots
- Open Graph + Twitter Card tags
- `SoftwareApplication` JSON-LD with detailed `featureList`
- Tab-pattern study mode explorer (`role="tablist"`/`"tab"`/`"tabpanel"`, `aria-selected`/`aria-controls`) — consistent with quiz.md's pattern
- Semantic landmarks (`<main>`, `aria-labelledby` sections, skip link)

---

**Related docs:** [README](../README.md) · [ARCHITECTURE](../ARCHITECTURE.md) · [Notes Feature](notes.md) · [Quiz Feature](quiz.md) · [CONTRIBUTING](../CONTRIBUTING.md)