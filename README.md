# Command Board

A single-file, self-hosted visual **Life OS** — an infinite canvas where cards, connections, milestones, a daily planner, a journal, and an embedded AI assistant come together into one place to think, plan, and act. Built from scratch in vanilla HTML/CSS/JavaScript with no frameworks and no build step.

> Built to solve a real problem: organizing a broad spectrum of goals — income, career, skills, health, and long-term purpose — in a way that makes it obvious what to actually do today, instead of freezing under everything at once.

---

## Screenshots

<!-- Highest-impact thing you can add. Take a screenshot of your board, drop the image into the repo
     (or into /docs), and reference it here like:  ![Command Board](docs/screenshot.png) -->  

<img width="1710" height="1107" alt="Screenshot 2026-08-20 at 3 44 29 PM" src="https://github.com/user-attachments/assets/8beb9ad8-a443-4a7f-96ab-a5328b38fc6e" />


---

## Features

**Canvas**
- Infinite pannable, zoomable canvas with a live minimap
- Drag empty space or hold Space to pan; scroll to zoom; Fit and 1:1 view controls

**Cards**
- Draggable cards with a focus statement, checkable action items, and a progress bar
- Per-card **Tasks**, **Notes**, and **Links** tabs
- Collapse cards to just the title bar; duplicate, color-code, and branch
- Deep-work focus view for working a single card

**Connections**
- Draw curved SVG links between cards to map flows and dependencies
- Color-coded connection types (feeds into / blocks / depends on), with labels, reverse, and delete

**Milestones & notes**
- Milestone markers for goals and checkpoints
- Freeform sticky notes anywhere on the canvas

**Daily planner sidebar**
- Today's focus, quick-add card, and a brain-dump capture area
- Morning / Midday / Evening schedule — drag action items from cards into a time block
- Weekly reset clears checkboxes without touching structure

**Journal**
- Dated journal entries with create / open / delete, stored locally

**Embedded AI assistant**
- Optional in-app assistant powered by the Anthropic API, with a chat panel and a knowledge-base tab
- Uses your own API key, entered at runtime and stored only in your browser (see Security below)

**Persistence**
- Dual-layer save: browser localStorage for session continuity, plus portable JSON export/import you fully own
- Auto-saves as you work; export a `.json` to move a board across machines

**Design**
- Dark, focused UI — near-black theme, muted accents, DM Mono and Instrument Serif typography

---

## Tech stack

- **HTML / CSS / JavaScript** — a single self-contained file, no frameworks, no build step
- **SVG** — curved connection rendering
- **Canvas 2D** — minimap
- **localStorage + JSON export/import** — dual-layer persistence
- **Anthropic API** — optional embedded AI assistant (browser-direct calls with a user-supplied key)
- **Electron** — packages the web app into a native desktop application

---

## Running it

### As a web app
1. Download `index.html`
2. Open it in any modern browser
3. It runs entirely locally — no server, no build

### As a desktop app (Electron)
```bash
npm install
npm start
```

---

## Saving and loading your work

Your board lives in a portable `.json` file that you own:
- **Export** (or Ctrl/Cmd+S) downloads a `.json` save file
- **Load save** restores a board exactly as you left it

Keep that `.json` anywhere — a folder, USB, or cloud drive — to pick up on any computer.

---

## Security

The optional AI assistant calls the Anthropic API directly from the browser using a key you enter at runtime. A few things worth knowing:

- Your API key is stored only in your browser's localStorage — it is **never** written into the source file.
- **Never paste a real API key into the HTML source, and never commit one to this repo.** Public keys get scraped from GitHub within minutes and can run up charges.
- Browser-direct API calls are appropriate for a personal, local tool. For any shared or hosted deployment, calls should be proxied through a backend so the key is never exposed to the client.

---

## Roadmap

- [ ] Package a distributable installer via Electron Forge
- [ ] Month-view calendar overlay
- [ ] Cross-board import
- [ ] Custom app icon and desktop polish

---

## Notes

- Some starter scaffolding was generated with AI assistance, then refactored, extended, and maintained manually across many iterations (currently v6).
- Ongoing manual feature development, refactoring, and documentation.

---

## Why this exists

This started as a way to visualize and act on a spread of life goals that were hard to hold in my head at once. It grew into a full single-file web app — with connections, planning, journaling, and an embedded assistant — and into a way to learn front-end architecture, state management, persistence, and desktop packaging by building something I actually use every day.
