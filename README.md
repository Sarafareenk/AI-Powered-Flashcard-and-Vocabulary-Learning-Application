# LexiLearn — AI-Powered Flashcard and Vocabulary Learning Application

> A desktop-first educational web application for college students who want to improve their English vocabulary through organised word collections, flashcards, quizzes, contextual examples, sentence practice, and personalised revision.

---

## 🚀 Getting Started

### No Installation Required

This application runs entirely in the browser with **no build step, no Node.js, and no server required**.

```
1. Open index.html in any modern browser (Chrome, Firefox, Edge, Safari)
   — simply double-click the file, or right-click → Open With → Browser
```

That's it. The app loads React, Tailwind CSS, and all icons from CDN on first open.

> **Requires an internet connection on first load** for CDN assets (React, Tailwind CSS, Google Fonts). After the first visit, browsers typically cache these assets.

---

## ✨ Features

| Feature | Description |
|---|---|
| **Dashboard** | Welcome summary, daily word, quick stats, recent activity, revision preview |
| **Vocabulary Library** | 30 curated words with search, category filter, and difficulty filter |
| **Word Details** | Full definition, phonetic, example, synonyms, memory tip, revision action |
| **Flashcards** | Flip animation, Known/Revision marking, shuffle, session progress, summary |
| **Vocabulary Quiz** | 10 MCQ questions, answer feedback, score tracking, retry option |
| **Sentence Practice** | Write a sentence, rule-based feedback, example sentence, memory tips |
| **Progress & Revision** | Real stats, quiz history, category breakdown, revision list management |
| **Settings & Help** | How-it-works guide, AI transparency notice, reset with confirmation |

---

## 📂 Project Structure

```
UIUX/
├── index.html          # Complete self-contained application
├── README.md           # This file
├── FIGMA_HANDOFF.md    # Design tokens and Figma prototype guide
└── src/
    ├── data/
    │   └── vocabulary.js   # Vocabulary dataset (reference copy)
    └── utils/
        └── storage.js      # localStorage helpers (reference copy)
```

> The application is entirely self-contained within `index.html`. The `src/` files are reference copies for documentation purposes.

---

## 🏗️ Technical Architecture

- **React 18** (via CDN unpkg) — component-based UI
- **Babel Standalone** (via CDN) — JSX compilation in the browser
- **Tailwind CSS** (via CDN Play) — utility-first styling
- **Google Fonts** — Inter typeface
- **localStorage** — persistent learning state, no backend needed

### State Management

All application state is stored in a single object and persisted to `localStorage` under the key `lexilearn_v1`:

```js
{
  savedWords: [],          // word IDs in revision list
  knownWords: [],          // word IDs marked as known
  quizAttempts: [],        // { date, score, total, wordIds }
  practiceSessionsCount: 0,
  flashcardSessions: [],   // { date, known, revision }
  lastActivity: null
}
```

State flows top-down from the `<App>` root component, passed as props to each page. Updates use immutable patterns — new state objects are created and passed to both `setState` and `saveState`.

### AI / Rule-based Features

The project title includes "AI-Powered." In this version:

- All vocabulary content (definitions, examples, tips) is **hand-curated**
- Sentence practice feedback uses **local rule-based validation** (word presence, capitalisation, punctuation)
- No AI API key, external model, or network call is made
- The service layer is structured so a real AI API (Gemini, OpenAI) can be wired in without rewriting the UI

---

## 📚 Vocabulary Dataset

30 curated English words across 5 categories and 3 difficulty levels:

| Category | Count |
|---|---|
| Academic | 12 |
| Communication | 5 |
| Character | 5 |
| Science | 4 |
| Technology | 4 |

---

## 🎓 Learning Cycle

The application supports the complete vocabulary learning cycle:

```
Discover → Understand → Recall → Practise → Revise
(Library)   (Details)  (Cards) (Practice) (Progress)
```

---

## ⚠️ Known Limitations

1. **No build tooling** — Babel transpilation runs in the browser. Production applications should use Vite or Create React App with a proper build step.
2. **CDN dependency** — Requires internet for first load. Works offline after browser caching.
3. **No TypeScript** — The browser-based Babel setup uses JSX. Full TypeScript support requires a build step.
4. **AI features simulated** — All AI-powered functionality uses rule-based or curated content.
5. **localStorage limits** — Browser localStorage has a ~5–10 MB limit, sufficient for this app's data.
6. **No user accounts** — Progress is stored per-browser, not across devices.

---

## 🔮 Possible Future Improvements

- Migrate to Vite + React + TypeScript with proper build tooling
- Integrate Gemini API or OpenAI API for real AI sentence evaluation
- Add spaced repetition scheduling (SM-2 algorithm)
- Word audio pronunciation via Web Speech API or text-to-speech
- Custom word lists that users can create and edit
- Import/export progress as JSON for backup
- Dark mode using Tailwind's `dark:` classes
- PWA manifest for offline use and home screen installation
- Keyboard navigation and accessibility improvements
- Unit tests with Vitest and React Testing Library

---

## 🏛️ College Project Notes

- **Subject:** UI/UX Design and Software Development
- **Version:** 1.0 — October 2026
- **Stack:** React, Tailwind CSS, Vanilla JS (browser-based)
- **Data:** Curated vocabulary, no external APIs
- **AI Features:** Rule-based, clearly labelled as not AI-generated
