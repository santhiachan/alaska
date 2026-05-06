# Alaska Cruise Packing Checklist

A single-page travel companion for a 7-day Holland America voyage from **Vancouver → Whittier** through the Inside Passage, Glacier Bay, and College Fjord (May 9–17, 2026). Part interactive packing checklist, part trip journal — built as one self-contained HTML file.

🌐 **Live site:** [santhiachan.github.io/alaska](https://santhiachan.github.io/alaska/)

---

## What it does

### 📋 Packing list
- 10 categories curated for layered Alaska weather, small-boat tours, a helicopter excursion, and a scenic railroad.
- Live progress bar with packed-count and percentage.
- Filter chips to focus on one category at a time.
- A **"Must pack first"** group surfacing the critical items across categories.
- Add your own items, remove ones you don't need, or pin anything as priority.
- Everything you do is saved to your browser instantly. Sign in with Google to sync across devices via Cloud Firestore.

### 🗺 Itinerary & trip journal
- An 8-card itinerary covering every leg of the cruise with date, location, and the day's activity.
- **Click any day** to add a journal entry: free-form notes plus photo uploads (any number, drag-from-file or click-to-pick).
- Each click creates a **new entry** — so a single day can hold a morning note, an evening note, a photo dump from dinner, etc., each timestamped.
- All entries appear in a **Trip Journal** feed beneath the day cards. Edit any entry inline, delete individual entries, or click any photo for a full-screen lightbox.

### 🎨 Design
The whole thing runs on a small **Nordic-minimalist** design system: icy-blue accents over warm paper neutrals, Cormorant Garamond headings paired with Inter, soft watercolor map illustrations as the hero and body backgrounds, generous whitespace, and a calm, second-person voice throughout.

---

## Tech

- **Pure static HTML** — one file, no build step required to run.
- **Vanilla JS** for all interactivity (no frameworks).
- **Firebase Auth + Firestore** (optional) for cross-device sync. Without sign-in, everything persists locally via `localStorage`.
- **GitHub Pages** for hosting.

### Storage keys (local)
| Key | Purpose |
|---|---|
| `alaska-cruise-checklist-v1` | Checked-off items |
| `alaska-cruise-checklist-custom-v1` | User-added items |
| `alaska-cruise-checklist-removed-v1` | User-removed default items |
| `alaska-cruise-priority-v1` | "Must pack first" overrides |
| `alaska-cruise-journal-v1` | Trip journal entries (notes + photos) |
| `alaska-cruise-view-v1` | Last-viewed tab (itinerary / packing) |

---

## Files in this repo

- `Alaska Cruise Packing Checklist (standalone).html` — **the deployed file**: a single self-contained HTML with all assets inlined. This is what GitHub Pages serves.
- `Alaska Cruise Packing Checklist.html` — the working source (references external assets in `assets/`).
- `assets/` — hero map, background map, icon set, reference docs.
- `colors_and_type.css` — design-system tokens (color, type, spacing, radius, shadow, motion).
- `preview/` — design-system specimen cards.
- `ui_kits/checklist/` — JSX components mirroring the checklist UI.
- `firestore.rules` — Firestore security rules (each user can only read/write their own checklist).
- `SKILL.md` — agent skill manifest.

---

## Running locally

Just open `Alaska Cruise Packing Checklist (standalone).html` in any modern browser. No server, no build, no install.

To rebuild the standalone bundle from the working source, the inputs are `Alaska Cruise Packing Checklist.html` plus the `assets/` folder.

---

## Privacy

When signed out, your checklist and journal stay entirely in your browser — nothing leaves your device. Sign in with Google and your data syncs to a per-user document in Firestore (`users/<your-uid>/packingChecklist/alaskaCruise2026`); no one else can read it.

---

Bon voyage. ⚓
