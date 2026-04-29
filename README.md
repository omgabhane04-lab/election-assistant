# ElectED — Election Process Assistant 🗳️

An interactive, AI-powered civic education assistant that helps users understand election processes, timelines, and democratic institutions in a clear, approachable, and non-partisan way.

---

## 🏛️ Chosen Vertical

**Civic Education / Government Processes** — Helping everyday citizens understand how elections work, from voter registration to vote certification.

---

## 🎯 Approach & Logic

ElectED is a single-page web application that uses the **Claude AI API** (Anthropic) to power a conversational assistant focused exclusively on election education.

### Design Philosophy
- **Non-partisan**: The assistant strictly provides factual, procedural information — no opinions on candidates, parties, or policies.
- **Progressive disclosure**: Users can start from quick-topic chips or sidebar shortcuts, then dive deeper via conversation.
- **Civic accuracy**: The system prompt is carefully crafted to keep responses grounded in verified civic processes.

### Architecture
```
index.html (single file)
├── Header — branding & status
├── Sidebar — quick topics + visual timeline
├── Chat area — message history + welcome card
└── Input area — textarea + send button
```

All logic is client-side JavaScript with a direct call to `https://api.anthropic.com/v1/messages`.

---

## ⚙️ How the Solution Works

1. **User opens `index.html`** — the welcome card explains the assistant's purpose.
2. **Quick-topic shortcuts** in the sidebar or chip buttons let users start without typing.
3. **Conversation history** is maintained in-memory so multi-turn conversations stay coherent.
4. **AI responses** are formatted: `**bold**`, numbered steps, and bullet lists are converted to clean HTML for readability.
5. **System prompt** enforces non-partisan, civic-focused behavior at all times.

### Topics the assistant covers
- Voter registration (eligibility, deadlines, ID requirements)
- Types of elections: primary, general, runoff, special, local
- The Electoral College — how it works, faithless electors, tiebreakers
- Election Day step-by-step guide
- How votes are counted, tabulated, and certified
- Campaign finance: FEC rules, PACs, Super PACs, donation limits
- Ballot types: ranked choice voting, proportional representation, FPTP
- International election systems for comparison
- Historical context and landmark election reforms
- Election security and integrity

---

## 🔧 Setup & Running

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for AI API calls and Google Fonts)

### Steps
```bash
git clone https://github.com/<your-username>/elected-assistant
cd elected-assistant
# Open index.html in a browser
open index.html
```

> **Note:** The app calls the Anthropic API directly from the browser. For production deployment, proxy API calls through a backend to protect API keys.

---

## 🌐 Google Services Integration

- **Google Fonts** — `Playfair Display`, `DM Sans`, `DM Mono` loaded via `fonts.googleapis.com` for a polished typographic system.
- Designed for easy extension with **Google Cloud Functions** (serverless API proxy) and **Firebase Hosting** (one-command deploy).

---

## 📐 Assumptions Made

1. The app is intended as a civic education tool, not a voter lookup service.
2. Users are primarily interested in the **US election system**, but the assistant can address other countries' systems when asked.
3. No backend is required for the prototype — API calls are made client-side.
4. The assistant should refuse to endorse any candidate, party, or political position.

---

## ✅ Evaluation Checklist

| Area | Implementation |
|------|---------------|
| **Code Quality** | Single-file, well-commented HTML/CSS/JS; clear separation of concerns |
| **Security** | No secrets hardcoded; no data stored; inputs sanitized via DOM APIs |
| **Efficiency** | No frameworks/dependencies; ~100KB total; lazy-loaded fonts |
| **Accessibility** | Semantic HTML, keyboard navigation, ARIA-friendly structure, focus management |
| **Google Services** | Google Fonts integrated |
| **AI Logic** | Carefully engineered system prompt; multi-turn conversation history; structured formatting |

---

## 📁 Repository Structure

```
elected-assistant/
└── index.html        # Complete application (single file)
└── README.md         # This file
```

---

## 🎨 Design Notes

ElectED uses a **editorial newspaper aesthetic** — cream paper tones, ink blacks, accent reds — evoking the gravitas of civic discourse while remaining accessible and modern. Typography pairs `Playfair Display` (display headings) with `DM Sans` (body) and `DM Mono` (labels/metadata).

---

*Built for the Google Antigravity Challenge — Civic Education Vertical*
