# LexiLearn — Figma Design Handoff

> This document provides everything needed to recreate the LexiLearn web application as a high-fidelity Figma prototype. No native Figma file was auto-generated — use this guide to build the prototype from scratch in Figma, using the live web app as your visual reference.

---

## 1. Design Tokens

### Colour Palette

| Token | Hex | Usage |
|---|---|---|
| `primary-50` | `#eef2ff` | Background tints, hover states |
| `primary-100` | `#e0e7ff` | Sidebar active, tag backgrounds |
| `primary-200` | `#c7d2fe` | Borders on primary elements |
| `primary-400` | `#818cf8` | Progress bars, accents |
| `primary-500` | `#6366f1` | Icons, focus rings |
| `primary-600` | `#4f46e5` | Primary buttons, sidebar logo, links |
| `primary-700` | `#4338ca` | Button hover state |
| `surface-50` | `#f8fafc` | App background |
| `surface-100` | `#f1f5f9` | Card inner backgrounds |
| `surface-200` | `#e2e8f0` | Card borders, dividers |
| `surface-300` | `#cbd5e1` | Placeholder text backgrounds |
| `white` | `#ffffff` | Card backgrounds, sidebar |
| `slate-400` | `#94a3b8` | Secondary text, labels |
| `slate-500` | `#64748b` | Subtitle text, captions |
| `slate-600` | `#475569` | Body text |
| `slate-700` | `#334155` | Primary body text |
| `slate-800` | `#1e293b` | Headings |
| `slate-900` | `#0f172a` | Page titles, word headings |
| `emerald-400` | `#34d399` | Known progress bar |
| `emerald-50` | `#ecfdf5` | Known word tag background |
| `emerald-700` | `#047857` | Known word tag text |
| `amber-400` | `#fbbf24` | Revision progress bar |
| `amber-50` | `#fffbeb` | Revision tag background |
| `amber-700` | `#b45309` | Revision tag text |
| `rose-50` | `#fff1f2` | Error/Hard background |
| `rose-700` | `#be123c` | Error/Hard text |

### Category Colours

| Category | Background | Text |
|---|---|---|
| Academic | `#e0e7ff` | `#4338ca` |
| Communication | `#ede9fe` | `#6d28d9` |
| Character | `#fff7ed` | `#c2410c` |
| Science | `#ecfeff` | `#0e7490` |
| Technology | `#eff6ff` | `#1d4ed8` |

---

## 2. Typography Scale

| Level | Size | Weight | Line Height | Usage |
|---|---|---|---|---|
| Page Title | 24px / 1.5rem | 700 | 1.3 | `<h1>` page headings |
| Section Title | 18px / 1.125rem | 600 | 1.4 | Card headers |
| Word Display | 30px / 1.875rem | 700 | 1.2 | Word detail hero, flashcard front |
| Word Display (sm) | 24px / 1.5rem | 700 | 1.2 | Word in library grid |
| Body | 14px / 0.875rem | 400 | 1.625 | Descriptions, definitions |
| Body Medium | 14px / 0.875rem | 500 | 1.625 | Button labels, nav items |
| Caption | 12px / 0.75rem | 400 | 1.5 | Tags, metadata, hints |
| Caption Bold | 12px / 0.75rem | 600 | 1.5 | Category labels (uppercase) |

**Font Family:** Inter — import from Google Fonts or use system-ui fallback.

---

## 3. Spacing & Layout

| Token | Value | Usage |
|---|---|---|
| `space-1` | 4px | Tight gaps (tag internals) |
| `space-2` | 8px | Inner element gaps |
| `space-3` | 12px | Button internal padding |
| `space-4` | 16px | Card internal padding (sm) |
| `space-5` | 20px | Card internal padding (md) |
| `space-6` | 24px | Page padding |
| `space-7` | 28px | Word detail padding |
| `space-8` | 32px | Section gaps |

### Layout Grid

| Element | Value |
|---|---|
| Sidebar width | 240px |
| Content max-width | 896px (library), 640px (flashcards, quiz, practice) |
| Viewport target | 1440 × 900 |
| Content left pad | 24px |
| Content right pad | 24px |
| Column gap | 16px–20px |

---

## 4. Corner Radii

| Usage | Radius |
|---|---|
| Tags / Chips | 9999px (pill) |
| Buttons | 8px |
| Cards | 12px |
| Modals | 16px |
| Flashcard | 16px |
| Input fields | 8px |
| Large callout blocks | 8px |
| Sidebar nav items | 8px |
| Stats cards | 12px |

---

## 5. Shadows

| Type | CSS Value | Usage |
|---|---|---|
| Card shadow | `0 1px 3px rgba(0,0,0,.07), 0 1px 2px rgba(0,0,0,.07)` | All cards |
| Modal shadow | `0 20px 60px -10px rgba(0,0,0,.2)` | Confirmation modals |
| Hover card | `0 8px 25px -5px rgba(99,102,241,.15)` | Hovered vocabulary cards |

---

## 6. Component Inventory

### Atoms

| Component | Description |
|---|---|
| **Tag / Chip** | Pill-shaped label. Variants: difficulty (Easy/Medium/Hard), category, known |
| **Button** | Variants: primary (indigo), secondary (white+border), ghost, danger, success. Sizes: sm, md, lg |
| **Progress Bar** | Full-width track + coloured fill. Animated width transition |
| **Input** | Text input with border, rounded, focus ring |
| **Textarea** | Multi-line input for sentence practice |
| **Select** | Styled native `<select>` for filters |

### Molecules

| Component | Description |
|---|---|
| **Word Card** (library grid) | Word, phonetic, tags, definition preview, save pin, view link |
| **Stat Card** | Icon, large number, label text |
| **Sidebar Nav Item** | Icon + label, active and hover states |
| **Flashcard** | Two-sided flip card: front (word + tags), back (indigo, definition + example) |
| **Quiz Option** | Bordered button, states: default, correct (green), incorrect (red), disabled |
| **Revision List Item** | Word name, category, difficulty tag, remove button |
| **Activity Item** | Icon + description + time ago |
| **Empty State** | Icon + title + description + optional CTA |

### Organisms

| Component | Description |
|---|---|
| **Sidebar** | 240px fixed left panel: logo, nav items, version footer |
| **PageHeader** | Title + subtitle + optional action buttons (top of each page) |
| **Dashboard Stats Row** | 4-column grid of Stat Cards |
| **Daily Word Card** | Featured word with flip actions and tags |
| **Modal** | Overlay + centred card, used for confirmations |
| **Quiz Feedback Block** | Conditional result box below quiz options |
| **Progress Chart Block** | Category-labelled progress bars |

---

## 7. Screen Inventory

| Screen | Route Key | Layout |
|---|---|---|
| Dashboard | `dashboard` | 3-col (2+1): stat row + daily word + activity + quick actions + progress + revision |
| Vocabulary Library | `library` | Filter bar + 2-col word grid |
| Word Details | `detail` | Single centred card (max 640px) |
| Flashcards | `flashcards` | Single centred (max 512px) — progress + flip card + controls |
| Quiz | `quiz` | Single centred (max 512px) — progress + question card |
| Sentence Practice | `practice` | Single centred (max 672px) — word info + textarea + feedback + example |
| Progress & Revision | `progress` | Stats row + 2-col (quiz history + category chart) + revision list |
| Settings & Help | `settings` | Single centred (max 672px) — stacked sections |

---

## 8. Main User Flows (Prototype Connections)

```
[Dashboard]
  → Click "View Details" on Daily Word       → [Word Details]
  → Click flashcard quick-action card        → [Flashcards]
  → Click quiz quick-action card             → [Quiz]
  → Click "View all" on Revision list        → [Progress & Revision]

[Vocabulary Library]
  → Click word title or "View details →"    → [Word Details]
  → Click 📌 icon                            → toggle saved state (same screen)

[Word Details]
  → Click "← Back to Library"               → [Vocabulary Library]
  → Click "✍️ Practice Writing"             → [Sentence Practice]
  → Click "📌 Save to Revision"             → toggle saved state

[Flashcards]
  → Tap card                                 → flip to definition side
  → Click "✓ Known"                          → mark known, advance
  → Click "↻ Revision"                       → mark revision, advance
  → Complete all cards                        → [Session Summary screen]
  → Click "New Session"                       → restart shuffled deck

[Quiz]
  → Click answer option                      → show feedback
  → Click "Next Question →"                  → next question
  → Click "See Results 🏆"                   → [Results screen]
  → Click "Retry Quiz"                        → new randomised quiz

[Sentence Practice]
  → Click "Check My Sentence"               → show rule-based feedback
  → Click "Try Another Word"                → new random word

[Progress & Revision]
  → Click word name in revision list        → [Word Details]
  → Click ✕ on revision item               → confirmation modal → remove

[Settings & Help]
  → Click "Reset All Progress"              → confirmation modal → reset
  → Click quick nav buttons                → respective page
```

---

## 9. Recreating in Figma — Practical Steps

### Step 1: Setup

1. Open Figma and create a new file: **LexiLearn — UI/UX Prototype**.
2. Set up a **Frame** at `1440 × 900` (Desktop target).
3. Create a **Styles library**:
   - Add all colours from Section 1 as Colour Styles.
   - Add all text styles from Section 2 as Text Styles.

### Step 2: Component Library

1. Create a **Components** page.
2. Build each component listed in Section 6 as a Figma Component (`Ctrl+Alt+K`).
3. Use **Variants** for Button (variant + size), Tag (type), Quiz Option (state).
4. Define **Auto Layout** on all components for resize behaviour.

### Step 3: Screens

1. Create one frame per screen listed in Section 7.
2. Use the **live web app** as a visual reference — open `index.html` and screenshot each page at 1440 × 900.
3. Paste screenshots as reference layers (locked, 30% opacity) and rebuild each screen using your components.

### Step 4: Prototype Connections

1. Switch to **Prototype** tab in Figma.
2. Add connections following the flows in Section 8.
3. Use **Navigate to** interactions with **Instant** or **Smart Animate** transitions.
4. Designate the Dashboard as the **Starting Frame**.

### Step 5: Handoff Inspection

1. Invite reviewers with "can view" access.
2. Developers can use the **Inspect** panel to view exact measurements, colours, and fonts.

---

## 10. Web App vs Figma Prototype

| | Web Application (`index.html`) | Figma Prototype |
|---|---|---|
| **Purpose** | Functional product demo | Design documentation + clickable prototype |
| **Interactivity** | Fully functional (real state, real localStorage) | Simulated clicks and page transitions only |
| **Data** | 30 real vocabulary words, persistent progress | Static screenshots or static component fills |
| **AI features** | Rule-based, clearly labelled | Depicted as if functional in design screens |
| **Editing** | Edit source code in `index.html` | Edit component library in Figma |
| **Sharing** | Open HTML file in any browser | Share Figma link (view/edit) |

---

*LexiLearn — College UI/UX Project · October 2026*
