<p align="center">
  <img src="https://user-images.githubusercontent.com/61057666/169029838-74df663d-2e62-4d77-bdff-b43f7d63f00f.png" width="100%" />
</p>
<h1 align="center">Anmol Yadav</h1>
<p align="center"><b>Backend Engineer · Multi-Agent Systems · Production NLP</b></p>
<p align="center"><i>I build systems that know when they don't know enough, then loop until they do.</i></p>

---

I build LLM systems that ship — multi-agent orchestration, efficient fine-tuning, and RAG pipelines designed around one question: how much complexity can you hide before the system stops being useful?*

---

studying Final year, what doesn't fit in a lecture hall.

---

```
focus     : backend engineering · multi-agent systems · efficient LLMs · RAG pipelines 
currently : open to SDE 1 & Backend internships & full-time opportunities
location  : Earth, India
```

---

### What I Actually Build

| Project | The Question I Was Answering | Result |
|---|---|---|
| [Vortex-Multi-Agent-Ai](https://github.com/Anmol1578/Vortex-Multi-Agent-Ai) | Can one router hide 8 specialist agents behind a single prompt box, without the routing logic leaking into the UI? | LangGraph `StateGraph` router + credit gate dispatching to 8 agents (chat, search, coding, PDF, PDF-RAG, PPT, vision, image analysis); Node microservices (gateway, auth, chat, billing, agent), Qdrant RAG, Redis rate-limiting, Razorpay billing |
| [Cyvion-Chat](https://github.com/Anmol1578/Cyvion-Chat) | How much real-time infrastructure can you bolt onto a chat app before the socket layer *is* the product? | Socket.IO real-time messaging, Clerk auth with webhook-synced user data, read receipts / typing / online presence, Dockerized SPA+API monolith with cron jobs |
| [Travel-AI-Itinerary](https://github.com/Anmol1578/Travel-AI-Itinerary) | Can one LLM call replace a day of manual trip planning and still come back structured, not just a wall of text? | Full-stack MERN app, JWT + bcrypt auth, Gemini-generated day-by-day itineraries persisted per user, Axios-interceptor-driven env routing |
| [Snap-Text](https://github.com/Anmol1578/Snap-Text) | Can you snip and OCR text off a locked-down video player without a server ever seeing a frame? | Manifest V3 Chrome extension, Tesseract.js OCR running in an offscreen Web Worker, zero network calls — full pipeline runs client-side |
| [Movie-Watchlist-Api](https://github.com/Anmol1578/Movie-Watchlist-Api) | How much of a "real" backend — auth, relational integrity, validation — can you build with zero frontend at all? | JWT + bcrypt auth, Prisma 7 relational schema with composite unique constraints, Zod-validated REST API, deployed on Render |

---

## Projects

### ⚡ Vortex — Multi-Agent AI Platform
*[GitHub](https://github.com/Anmol1578/Vortex-Multi-Agent-Ai)*

**The problem:** Most "AI chat apps" point every request at one generic model and hope the prompt is good enough. That works until someone asks for a PDF, then a slide deck, then wants to chat about an uploaded image — one model can't specialize in all of it without either bloating its prompt or degrading everywhere.

**What I built:** A production-shaped multi-agent platform with an LLM-powered router sitting in front of 8 specialist agents — chat, search, coding, PDF generation, PDF/RAG Q&A, PPT generation, image generation, and image analysis. Built on LangGraph's `StateGraph`, every request flows through explicit nodes (`router → credit → <agent> → end`) instead of if/else spaghetti. The router reads the prompt *and* any attached file, then returns a primary agent + fallback as structured JSON.

**The key decision:** File type decides the domain (PDF-family vs. image-family), but the user's wording decides intent — read vs. generate. An empty prompt with a file attached always defaults to the safer "read/analyze" agent instead of guessing at generation. Credits are deducted *before* the agent runs, so a failed generation never silently wastes a user's balance twice.

**Infra:** Node.js microservices (gateway, auth, chat, billing, agent) · MongoDB · Redis-backed sliding-window rate limits · Qdrant for RAG retrieval · Razorpay billing with real plan tiers · React 19 + Redux Toolkit frontend with a dedicated Artifact Panel for generated files/images/code

`Node.js` `LangGraph` `React` `MongoDB` `Redis` `Qdrant` `Razorpay` `Docker`

[→ View Repository](https://github.com/Anmol1578/Vortex-Multi-Agent-Ai)

---

### 💬 Cyvion — Real-Time Messaging Platform
*[GitHub](https://github.com/Anmol1578/Cyvion-Chat) · [Live Demo ↗](https://cyvion-chat.onrender.com)*

**The problem:** A chat app isn't just message send/receive — it's presence, delivery state, and social signals happening constantly and simultaneously. Most tutorials skip straight to "messages appear," ignoring the read receipts, typing indicators, and online status that actually make a chat app feel real-time.

**What I built:** A full-stack messaging platform where Socket.IO drives bidirectional communication for messages, typing indicators, read receipts, and live presence dots — all layered on top of Clerk-based auth with webhook-synced user data. The whole thing ships as an SPA+API monolith: Express serves both the REST API and the built React frontend from one server.

**The key decision:** Auth state lives in a Zustand store that stays synced with Clerk's session lifecycle rather than duplicating session logic — one source of truth instead of two systems drifting apart.

**Infra:** Multi-stage Dockerfile (frontend build → backend build → lean runtime) with a non-root container user · Clerk webhook signature verification to prevent spoofing · scheduled cron cleanup jobs · CORS scoped to a known frontend origin

`React` `Express` `Socket.IO` `MongoDB` `Clerk` `Zustand` `Docker`

[→ View Repository](https://github.com/Anmol1578/Cyvion-Chat) · [→ Live Demo](https://cyvion-chat.onrender.com)

---

### ✈️ AI Travel Itinerary Planner
*[GitHub](https://github.com/Anmol1578/Travel-AI-Itinerary) · [Live Demo ↗](https://travel-ai-itinerary-2.onrender.com)*

**The problem:** Planning a multi-day trip means juggling logistics, pacing, and "did I actually cover everything" — the kind of structured-but-tedious task LLMs are well-suited for, if you can get them to return something usable instead of a wall of prose.

**What I built:** A full-stack MERN app where trip details go to Google's Gemini API and come back as a structured, day-by-day itinerary — persisted per user in MongoDB, not just displayed and forgotten. JWT + bcrypt handle auth; a global Axios interceptor layer attaches tokens and routes requests to the right environment automatically, keeping that logic out of individual components.

**The key decision:** CORS is explicitly scoped to known frontend origins instead of left open — a small thing most side projects skip that matters the moment this touches production.

**Infra:** React 18 + Vite · Tailwind CSS v4 glassmorphic UI · SPA catch-all rewrite so client-side routes survive a refresh · environment-aware config for local vs. production

`React` `Node.js` `Express` `MongoDB` `Gemini API` `JWT`

[→ View Repository](https://github.com/Anmol1578/Travel-AI-Itinerary) · [→ Live Demo](https://travel-ai-itinerary-2.onrender.com)

---

### 📸 SnapText — Offline OCR for YouTube
*[GitHub](https://github.com/Anmol1578/Snap-Text)*

**The problem:** Code snippets, subtitles, and on-screen text in YouTube videos are all pixels, not text — you either pause and retype by hand or give up.

**What I built:** A Manifest V3 Chrome extension that lets you draw a box over any region of a YouTube video and instantly copies the text inside it to your clipboard. OCR runs entirely in-browser via Tesseract.js inside a Web Worker — no server call, no data ever leaves the machine.

**The key decision:** Running OCR in an Offscreen Document rather than the content script itself, isolating it from YouTube's page CSP while still keeping the whole pipeline local. Frame preprocessing (upscaling, contrast stretching, dark-mode inversion) was tuned specifically for video frames, which behave very differently from scanned documents.

**Infra:** Minimal permission footprint (`offscreen` only) · bundled Tesseract.js core + language data, zero external calls at runtime

`JavaScript` `Chrome Extension (MV3)` `Tesseract.js` `Web Workers`

[→ View Repository](https://github.com/Anmol1578/Snap-Text)

---

### 🎬 Movie Watchlist API
*[GitHub](https://github.com/Anmol1578/Movie-Watchlist-Api) · [Live API ↗](https://movie-watchlist-api-m5sx.onrender.com)*

**The problem:** Most portfolio backend projects lean on a frontend to hide gaps in the API itself. I wanted a project where the backend had nowhere to hide — no UI, no client, just the API standing on its own.

**What I built:** A backend-only REST API for movies and personal watchlists with real relational modeling: Users, Movies, and WatchlistItems connected through foreign keys and cascade deletes, with a composite unique constraint (`@@unique([userId, movieId])`) preventing duplicate watchlist entries at the database level rather than in application code.

**The key decision:** Validation with Zod happens before any request reaches the database — `movieId` must be a UUID, `rating` must be 1–10, `status` must match an enum. Invalid data never gets a chance to touch Prisma.

**Infra:** PostgreSQL + Prisma 7 with the `PrismaPg` driver adapter · JWT stored in an `httpOnly` cookie · bcrypt password hashing · deployed on Render with graceful shutdown handling

`Node.js` `Express` `PostgreSQL` `Prisma` `Zod` `JWT`

[→ View Repository](https://github.com/Anmol1578/Movie-Watchlist-Api) · [→ Live API](https://movie-watchlist-api-m5sx.onrender.com)

---

## Skills

**Backend:** Node.js · Express · Python · Microservices Architecture · REST APIs
**LLMs & Agents:** LangGraph · LangChain · Groq API · Google Gemini API · OpenRouter · Tavily
**Databases:** MongoDB · Mongoose · PostgreSQL · Prisma · Redis (ioredis) · Qdrant (vector DB)
**Auth & Security:** JWT · bcrypt · Firebase Admin · Clerk · Zod validation
**Frontend:** React · Redux Toolkit · Zustand · React Router · Tailwind CSS · Vite
**Real-Time & Extensions:** Socket.IO · Chrome Extension (Manifest V3) · Tesseract.js (OCR) · Web Workers
**Infra & Deployment:** Docker · AWS S3 · Render · Razorpay (payments) · pdfkit/pptxgenjs (document generation)

---

## Achievements
- 🥇 Finalist — DecodeX Hackathon 2024
- 🥇 Finalist — OpenAI X NamasteDev Hackathon
---

## Connect

<p align="center">
  <a href="mailto:anmol1578y@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/anmol-yadav5">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="">
    <img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=netlify&logoColor=white" />
  </a>
  <a href="https://x.com/Anmol1578">
    <img src="https://img.shields.io/badge/Twitter(X)-000000?style=for-the-badge&logo=twitter&logoColor=white" />
  </a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Anmol1578&color=00ff41&style=flat-square&label=Profile+Views" alt="Profile Views">
</p>

<p align="center"><sub>⚡ Open to SDE 1 & Backend internships & full-time opportunities</sub></p>
<p align="center"><sub><i>P.S. If you've read this far, either my SEO worked or you're genuinely curious. Either way — hi, let's talk.</i></sub></p>
