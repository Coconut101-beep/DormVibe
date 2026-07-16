# DormVibe 🏠✨

> An AI-powered dorm-styling assistant that turns a 60-second “vibe quiz” into a complete room design package — mood board, audio walkthrough, and a ready-to-buy shopping list.

DormVibe helps college students design a room they love without the overwhelm of browsing hundreds of products. Answer a short quiz about your style, budget, and priorities, and the app generates a personalized room concept, a narrated walkthrough, and curated products — including a peer-to-peer second-hand marketplace to keep it affordable and sustainable.

---

## 🏆 Awards

DormVibe was recognized at UNNC AI-Hackathon 2026:

- 🥈 **Second Place** — Overall
- 💡 **Most Valuable Business Idea**

---

## 🔗 Live Demo & Screenshots

- **Live demo:** [Live Demo](docs/Live_Demo.mp4)
- **Preview**: https://github.com/user-attachments/assets/e2324173-9a15-43cd-9f38-375da9a60316
- **Screenshots:** Available in [docs/Screenshots]

---

## 🎯 The Problem

Incoming students want a dorm that feels like *theirs*, but they face three friction points:

1. **Decision overload** — endless furniture and decor options with no sense of what works together.
2. **Budget pressure** — students are price-sensitive and often can't justify buying everything new.
3. **No visualization** — it's hard to picture a finished room before spending money.

DormVibe compresses “inspiration → plan → purchase” into a single guided flow.

## 💡 The Solution & Product Flow

```
Vibe Quiz  →  AI Generation  →  Mood Board / Room DNA  →  Customize  →  Shopping List + Marketplace  →  Checkout
```

1. **Vibe Quiz** — captures interests, color palette, budget, and room priority.
2. **Real-time generation** — live progress updates while the AI builds the concept (via Server-Sent Events).
3. **Mood Board** — AI-generated images of the styled room.
4. **Audio Walkthrough** — narrated explanation of the design choices.
5. **Shopping List** — curated products with retail links.
6. **Second-Hand Marketplace** — peer-to-peer listings so students can buy/sell used items affordably and sustainably.
7. **Checkout** — cart and checkout flow to complete the plan.

## 🌟 Key Features

| Feature | What it does |
|---|---|
| **Vibe Quiz** | Interactive interest / palette / budget / priority capture that drives personalization |
| **AI Mood Board** | High-quality generated room imagery from quiz inputs |
| **Audio Walkthrough** | AI-narrated tour explaining the room setup |
| **Recommendation logic** | Matches products to the student's style and budget |
| **Second-Hand Marketplace** | Peer-to-peer listings (price, pickup location, condition, free items) |
| **Checkout Flow** | Cart management through to checkout |

---

## 🏗️ Architecture

DormVibe is a full-stack TypeScript app with a React frontend and an Express backend that orchestrates the MiniMax AI APIs (text, image, and text-to-speech). Generation progress is streamed to the client in real time via Server-Sent Events.

```
User Browser  →  React (Vite) Frontend  →  Express Backend  →  MiniMax AI APIs (text · image · TTS)
                                              └→ SSE stream (live generation progress)
```

Deeper documentation lives in [`docs/`](docs):

- [Product Requirements (PRD)](docs/PRODUCT_REQUIREMENTS.md)
- [Technical Architecture](docs/TECHNICAL_ARCHITECTURE.md)

## 🧰 Tech Stack

- **Frontend:** React 18 (Vite), TypeScript, Tailwind CSS, Framer Motion, Zustand, React Router
- **Backend:** Node.js, Express, Axios
- **AI:** MiniMax API (text, image, TTS)
- **Realtime:** Server-Sent Events (SSE) for live generation progress
- **Deployment:** Vercel

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- npm (ships with Node.js)
- A MiniMax API key ([get one here](https://www.minimaxi.com))

### Installation

```bash
# 1. Clone the repository
git clone <repository-url>
cd dormvibe

# 2. Install dependencies
npm install

# 3. Set up environment variables
cp .env.example .env
# then open .env and add your MiniMax API key
```

### Running the app

```bash
npm run dev
```

- **Frontend:** Vite prints the URL (usually `http://localhost:5173/`)
- **Backend:** runs at `http://localhost:3001` (the frontend proxies API requests automatically)

> ⚠️ Never commit your `.env` file or expose your API key in frontend code. The app writes AI-generated images and audio to `api/public/generated/` at runtime — these are gitignored and recreated automatically.

---

## 📂 Project Structure

```
src/       React frontend (pages, components, store, hooks)
api/       Express backend (routes + MiniMax service integrations)
shared/    Shared TypeScript types
public/    Static assets
docs/      Product requirements (PRD) & technical architecture
```

---

## 📜 License

This project was built for educational purposes.
