<p align="center">
  <img src="https://user-images.githubusercontent.com/61057666/169029838-74df663d-2e62-4d77-bdff-b43f7d63f00f.png" width="100%" />
</p>
<h1 align="center">Anmol Yadav</h1>
<p align="center"><b> Backend Engineer — RAG Systems & Agent Architecture</b></p>

---

I build the backend systems behind LLM applications: REST APIs, RAG pipelines, vector search, and agent workflows, engineered for reliability, low latency, and clean service boundaries. My design question: how much complexity can the backend hide before the system stops being useful?

## What I'm Working On

- **Building:** RAG pipelines, agentic workflows, background job systems, and cloud-integrated backend services
- **Sharpening:** Data Structures & Algorithms, Low-Level Design, Advanced SQL, and backend system design
- **Exploring next:** Multi-agent orchestration, retrieval evaluation, and distributed job queues at scale

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

### Vortex — Multi-Agent AI Platform
Multi-agent platform where a LangGraph router with a credit gate dispatches to 8 specialist agents: chat, search, coding, PDF, PDF-RAG, PPT, vision, and image analysis.

[![Repository](https://img.shields.io/badge/Repository-15304A?style=flat-square&logo=github&logoColor=white)](https://github.com/Anmol1578/Vortex-Multi-Agent-Ai)
[![Live demo](https://img.shields.io/badge/Live_demo-3DD6C3?style=flat-square)](https://vortex-multi-agent-ai.vercel.app/)

![Node.js](https://img.shields.io/badge/Node.js-15304A?style=flat-square&logo=nodedotjs&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-15304A?style=flat-square&logo=langchain&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-15304A?style=flat-square&logo=qdrant&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-15304A?style=flat-square&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-15304A?style=flat-square&logo=mongodb&logoColor=white)
![Razorpay](https://img.shields.io/badge/Razorpay-15304A?style=flat-square&logo=razorpay&logoColor=white)

---

### Cyvion — Real-Time Messaging Platform
Real-time messaging with typing indicators, read receipts, and live presence, backed by webhook-synced authentication.

[![Repository](https://img.shields.io/badge/Repository-15304A?style=flat-square&logo=github&logoColor=white)](https://github.com/Anmol1578/Cyvion-Chat)
[![Live demo](https://img.shields.io/badge/Live_demo-3DD6C3?style=flat-square)](https://cyvion-chat.onrender.com)

![React](https://img.shields.io/badge/React-15304A?style=flat-square&logo=react&logoColor=white)
![Express](https://img.shields.io/badge/Express-15304A?style=flat-square&logo=express&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-15304A?style=flat-square&logo=socketdotio&logoColor=white)
![Clerk](https://img.shields.io/badge/Clerk-15304A?style=flat-square&logo=clerk&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-15304A?style=flat-square&logo=mongodb&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-15304A?style=flat-square&logo=docker&logoColor=white)

---

### AI Travel Itinerary Planner
Gemini-generated day-by-day itineraries, persisted per user.

[![Repository](https://img.shields.io/badge/Repository-15304A?style=flat-square&logo=github&logoColor=white)](https://github.com/Anmol1578/Travel-AI-Itinerary)
[![Live demo](https://img.shields.io/badge/Live_demo-3DD6C3?style=flat-square)](https://travel-ai-itinerary-2.onrender.com)

![React](https://img.shields.io/badge/React-15304A?style=flat-square&logo=react&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-15304A?style=flat-square&logo=nodedotjs&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-15304A?style=flat-square&logo=mongodb&logoColor=white)
![Gemini API](https://img.shields.io/badge/Gemini_API-15304A?style=flat-square&logo=googlegemini&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-15304A?style=flat-square&logo=jsonwebtokens&logoColor=white)

---

### SnapText — Offline OCR Chrome Extension
Chrome extension that OCRs on-screen video text entirely client-side.

[![Repository](https://img.shields.io/badge/Repository-15304A?style=flat-square&logo=github&logoColor=white)](https://github.com/Anmol1578/Snap-Text)

![Chrome Extension MV3](https://img.shields.io/badge/Chrome_Extension_MV3-15304A?style=flat-square&logo=googlechrome&logoColor=white)
![Tesseract.js](https://img.shields.io/badge/Tesseract.js-15304A?style=flat-square)
![Web Workers](https://img.shields.io/badge/Web_Workers-15304A?style=flat-square)

---

### Movie Watchlist API
Backend-only REST API with relational integrity and schema validation.

[![Repository](https://img.shields.io/badge/Repository-15304A?style=flat-square&logo=github&logoColor=white)](https://github.com/Anmol1578/Movie-Watchlist-Api)
[![Live API](https://img.shields.io/badge/Live_API-3DD6C3?style=flat-square)](https://movie-watchlist-api-m5sx.onrender.com)

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15304A?style=flat-square&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-15304A?style=flat-square&logo=prisma&logoColor=white)
![Zod](https://img.shields.io/badge/Zod-15304A?style=flat-square&logo=zod&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-15304A?style=flat-square&logo=jsonwebtokens&logoColor=white)
![Render](https://img.shields.io/badge/Render-15304A?style=flat-square&logo=render&logoColor=white)

---

## Tech Stack

| Domain | Technologies & Capabilities |
|---|---|
| **Backend** | Node.js, Bun, Express, Python, REST APIs, microservices, authentication (JWT, bcrypt, Clerk, Firebase Admin), rate limiting, background jobs, Socket.IO |
| **AI / GenAI** | LangGraph, LangChain, RAG pipelines, vector search, AI agents, tool orchestration, prompt engineering, structured outputs (Zod), Gemini API, Groq, OpenRouter, Tavily |
| **Databases** | PostgreSQL, pgvector, Qdrant, MongoDB, Prisma, Redis |
| **Infrastructure** | Docker, AWS (S3), Render, Vercel, CLI design, sandboxed execution |
| **Frontend** | React, Redux Toolkit, Zustand, Tailwind CSS, Vite |

---

## Achievements
- 🥇 Finalist — DecodeX Hackathon 2024
- 🥇 Finalist — OpenAI X NamasteDev Hackathon
  
---
## Connect

<p align="center">
  <a href="mailto:anmol1578y@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/anmol-yadav5"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://x.com/Anmol1578"><img alt="X" src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" /></a>
</p>


<p align="center">
  <img alt="Profile views" src="https://komarev.com/ghpvc/?username=Anmol1578&label=Profile+views&color=3DD6C3&labelColor=15304A&style=flat-square" />
</p>

<p align="center"><sub>Open to SDE-1 and Backend Developer roles, internships and full-time.</sub></p>
<p align="center"><sub><i>P.S. If you've read this far, either my SEO worked or you're genuinely curious. Either way — hi, let's talk.</i></sub></p>
