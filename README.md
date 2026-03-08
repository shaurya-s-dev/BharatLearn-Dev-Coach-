<div align="center">

# 🇮🇳 BharatLearn Dev Coach

### *Your AI-Powered Mentor for Computer Science Students*

**Learn faster. Debug smarter. Ace your viva.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-bharat--learn--frontend.vercel.app-blue?style=for-the-badge&logo=vercel)](https://bharat-learn-frontend.vercel.app/home)
[![Backend API](https://img.shields.io/badge/Backend%20API-Render-green?style=for-the-badge&logo=render)](https://bharatlearn-backend.onrender.com/)
[![Built With](https://img.shields.io/badge/Built%20With-Next.js%20%7C%20Node.js%20%7C%20Groq%20AI-purple?style=for-the-badge)](https://github.com/shaurya-s-dev/BharatLearn-Dev-Coach-)

---

> **"Tell me and I forget. Teach me and I remember. Involve me and I learn."**
> — *Benjamin Franklin*
>
> BharatLearn is built on this belief. We give hints, not answers. We ask questions, not solutions.
> **We are not replacing the teacher — we are scaling the best parts of one.**

---

![TypeScript](https://img.shields.io/badge/TypeScript-81.6%25-3178C6?style=flat-square&logo=typescript)
![JavaScript](https://img.shields.io/badge/JavaScript-17.0%25-F7DF1E?style=flat-square&logo=javascript)
![CSS](https://img.shields.io/badge/CSS-1.4%25-1572B6?style=flat-square&logo=css3)

</div>

---

## 📌 Table of Contents

- [What is BharatLearn?](#-what-is-bharatlearn)
- [The Problem We Solve](#-the-problem-we-solve)
- [Key Features](#-key-features)
- [Live Links](#-live-links)
- [Tech Stack](#-tech-stack)
- [System Architecture](#-system-architecture)
- [Project Structure](#-project-structure)
- [Quick Start](#-quick-start)
- [Environment Variables](#-environment-variables)
- [Google OAuth Setup](#-google-oauth-setup)
- [API Endpoints](#-api-endpoints)
- [Security](#-security)
- [Hackathon Submission](#-hackathon-submission)
- [Team](#-team)

---

## 🎯 What is BharatLearn?

**BharatLearn Dev Coach** is an AI-powered learning assistant built specifically for Indian computer science students. It helps students debug code and understand programming concepts — not by giving them the answer, but by guiding them to discover it themselves.

The core philosophy: **No solutions — you fix it.**

When a student submits buggy code, the AI:
1. Identifies the **exact error type** (syntax / logic / concept gap)
2. Explains the **underlying concept** they are missing
3. Gives a **Socratic hint** that points them in the right direction
4. Never, under any circumstances, writes the fix for them

This is the difference between a student who memorises code and a student who actually **learns to debug**.

---

## ❗ The Problem We Solve

Most CS students in India understand theory from textbooks. But when they sit down to write and debug code, they get stuck. So what do they do?

They open ChatGPT, paste their code, and get a complete solution. They copy it, submit it — and learn **nothing**.

There is no tool that teaches them **how to think through a problem**. No mentor available at 11pm before a lab submission. No guide that works on 2G mobile data in tier-2 cities.

**BharatLearn is that mentor.**

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🐛 **Code Debugging Assistant** | Paste code in Python, Java, JS, C++, Go, TypeScript, or C. AI detects the error, labels it, explains the concept, gives a Socratic hint. No solutions ever. |
| 📝 **Adaptive Quiz Generator** | Pick any CS topic → 10 AI-generated questions (MCQ, Short Answer, Coding) with difficulty tags (Easy / Medium / Hard) and AI explanations on reveal. |
| 🎓 **Viva Question Predictor** | Upload your project code → AI analyses it across Correctness, Code Organisation, and Best Practices → generates 20 predicted viva questions with difficulty, marks, and type tags. |
| 📚 **AI Learning Plan** | Upload your semester syllabus → AI generates a 24-week personalised learning roadmap aligned to your university curriculum. |
| 📊 **Progress Dashboard** | Study streak tracker, weekly activity chart, topic mastery bars, 30-day heatmap, weak-area alerts, and quick-start action cards. |
| 🌐 **Multi-Language Support** | Explanations available in Hindi, Tamil, Telugu, and English. |
| 📱 **Mobile-First Design** | Fully responsive, works on low-end Android devices, optimised for 2G mobile data (under 1 KB per AI request). |

---

## 🔗 Live Links

| Resource | URL |
|---|---|
| 🌐 Live Frontend | [bharat-learn-frontend.vercel.app/home](https://bharat-learn-frontend.vercel.app/home) |
| ⚙️ Live Backend API | [bharatlearn-backend.onrender.com](https://bharatlearn-backend.onrender.com/) |
| 💻 GitHub Repository | [github.com/shaurya-s-dev/BharatLearn-Dev-Coach-](https://github.com/shaurya-s-dev/BharatLearn-Dev-Coach-) |

> **Note for judges:** No local setup required. Both frontend and backend are live and fully accessible.

---

## 🛠 Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| Next.js 14 + TypeScript | React framework, SSR, routing |
| Tailwind CSS | Utility-first styling |
| Recharts | Dashboard charts and activity graphs |
| Vercel | Deployment and global CDN |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express.js | REST API server |
| Passport.js | Google OAuth 2.0 authentication |
| express-session | Server-side session management |
| Helmet + CORS | Security headers and origin control |
| express-rate-limit | AI / auth / general rate limiting |
| Joi | Input validation and sanitisation |
| Render | Backend deployment |

### AI & Cloud
| Technology | Purpose |
|---|---|
| Groq LLM API | Fast AI inference (Claude / Llama models) |
| Amazon DynamoDB | Student progress and session state |
| Amazon S3 + CloudFront | Syllabus uploads, content delivery |
| Amazon CloudWatch | API monitoring and alerting |
| Amazon ElastiCache (Redis) | AI response caching, session tokens |
| AWS IAM | Role-based access, secrets management |

> **Future roadmap:** AWS Bedrock (Claude 3.5 Sonnet) + SageMaker fine-tuning on Indian CS syllabi once AWS access is provisioned.

---

## 🏗 System Architecture

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         USER INTERFACES                                 │
│  ┌──────────────────────────┐    ┌─────────────────────────────────┐    │
│  │  🌐 Web App (Next.js)    │    │  📱 Mobile Web (Responsive PWA)  │    │
│  │  Deployed on Vercel      │    │  Optimised for 2G / Android      │    │
│  └──────────────┬───────────┘    └───────────────┬─────────────────┘    │
└─────────────────┼─────────────────────────────────┼────────────────────┘
                  │           HTTPS Request          │
                  ▼                                  ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                           API GATEWAY                                   │
│         Node.js + Express  |  Deployed on Render                        │
│   Routes: /debug  /quiz  /viva  /learn  /dashboard                      │
│   Auth: JWT tokens  |  AWS IAM  |  Rate Limiting  |  Joi Validation      │
└──────────────────────────────────┬──────────────────────────────────────┘
                                   │  Route to Handler
                                   ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                        BACKEND SERVICES                                 │
│  ┌────────────────┐  ┌──────────────────┐  ┌──────────┐  ┌──────────┐  │
│  │  Code Analyzer │  │  Quiz Generator  │  │  Viva    │  │ Learning │  │
│  │  Lambda-style  │  │  Lambda-style    │  │  Pred.   │  │  Plan    │  │
│  └───────┬────────┘  └────────┬─────────┘  └────┬─────┘  └────┬─────┘  │
└──────────┼───────────────────┼────────────────-─┼────────────-┼────────┘
           └───────────────────┴──────────Prompt───┴─────────────┘
                                          │
                                          ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                            AI LAYER                                     │
│  Groq LLM API  |  < 2 second response  |  Hint-only, no solutions       │
│  Current: Claude / Llama  |  Future: AWS Bedrock (Claude 3.5 Sonnet)    │
└──────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│                           DATA LAYER                                    │
│  DynamoDB (progress)  |  S3 (files)  |  CloudWatch  |  ElastiCache      │
└─────────────────────────────────────────────────────────────────────────┘
```

**Full round-trip: under 2 seconds.**

---

## 📁 Project Structure

```
BharatLearn-Dev-Coach/
├── package.json                  ← Root: runs both servers with concurrently
│
├── backend/
│   ├── server.js                 ← All routes, auth, AI calls, security
│   ├── package.json
│   └── .env.example              ← Copy to .env and fill secrets
│
└── frontend/
    ├── src/
    │   ├── app/
    │   │   ├── layout.tsx
    │   │   ├── page.tsx           ← Home (Astra AI chat)
    │   │   ├── dashboard/
    │   │   │   └── page.tsx       ← Streak, mastery, weekly chart
    │   │   ├── debug/
    │   │   │   └── page.tsx       ← Code Debugging Assistant
    │   │   ├── quiz/
    │   │   │   └── page.tsx       ← Adaptive Quiz Generator
    │   │   ├── viva/
    │   │   │   └── page.tsx       ← Viva Question Predictor
    │   │   ├── learning/
    │   │   │   └── page.tsx       ← AI Learning Plan
    │   │   └── settings/
    │   │       └── page.tsx       ← Profile + Google OAuth
    │   └── components/
    │       └── Sidebar.tsx        ← Navigation sidebar
    ├── next.config.ts             ← Proxies /api/* → backend
    └── package.json
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- npm 9+

### 1. Clone the repository

```bash
git clone https://github.com/shaurya-s-dev/BharatLearn-Dev-Coach-.git
cd BharatLearn-Dev-Coach-
```

### 2. Install all dependencies

```bash
npm run setup
```

This installs packages for both `frontend/` and `backend/` in one command.

### 3. Configure environment variables

```bash
cp backend/.env.example backend/.env
```

Open `backend/.env` and fill in your secrets (see [Environment Variables](#-environment-variables) below).

### 4. Run both servers

```bash
npm run dev
```

This starts:
- **Frontend** → [http://localhost:3001](http://localhost:3001)
- **Backend** → [http://localhost:3000](http://localhost:3000)

The frontend automatically proxies `/api/*` and `/auth/*` to the backend — **you only need to open one URL**.

---

## 🔐 Environment Variables

Create `backend/.env` from `backend/.env.example`:

```env
# ── Server ──────────────────────────────────────────
PORT=3000
NODE_ENV=development
FRONTEND_URL=http://localhost:3001

# ── Session ─────────────────────────────────────────
SESSION_SECRET=<64-character-random-string>

# ── AWS ─────────────────────────────────────────────
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=<your-access-key>
AWS_SECRET_ACCESS_KEY=<your-secret-key>
BEDROCK_MODEL_ID=anthropic.claude-3-sonnet-20240229-v1:0

# ── Groq AI (current inference engine) ──────────────
GROQ_API_KEY=<your-groq-api-key>

# ── Google OAuth ─────────────────────────────────────
GOOGLE_CLIENT_ID=<client-id>.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=<your-client-secret>
```

> **Get a Groq API key free at:** [console.groq.com](https://console.groq.com)

---

## 🔑 Google OAuth Setup

1. Go to [console.cloud.google.com/apis/credentials](https://console.cloud.google.com/apis/credentials)
2. Click **Create Credentials → OAuth 2.0 Client ID**
3. Application type: **Web application**
4. Add Authorised redirect URI:
   ```
   http://localhost:3000/auth/google/callback
   ```
5. Copy **Client ID** and **Client Secret** → paste into `backend/.env`

For production, also add:
```
https://bharatlearn-backend.onrender.com/auth/google/callback
```

---

## 📡 API Endpoints

| Method | Route | Description |
|---|---|---|
| `POST` | `/api/debug` | Submit code → receive Socratic hint |
| `POST` | `/api/quiz` | Topic input → generate 10 questions |
| `POST` | `/api/viva` | Upload code → predict 20 viva questions |
| `POST` | `/api/learn` | Upload syllabus → generate learning plan |
| `GET` | `/api/dashboard` | Fetch student progress and streak data |
| `GET` | `/auth/google` | Initiate Google OAuth flow |
| `GET` | `/auth/google/callback` | OAuth callback handler |
| `GET` | `/auth/logout` | Clear session and log out |

All AI endpoints respond in **under 2 seconds**. All inputs are validated via Joi before reaching the AI layer.

---

## 🛡 Security

| Measure | Implementation |
|---|---|
| HTTP Headers | Helmet (15+ security headers) |
| CORS | Restricted to frontend origin only |
| Rate Limiting | AI: 10/min · Auth: 20/15min · General: 60/min |
| Input Validation | Joi schema validation on all endpoints |
| Session Security | httpOnly + sameSite cookies, server-side storage |
| Secrets | All API keys in backend `.env` only — none in frontend |
| Payload Limits | 32KB JSON · 10MB file uploads |
| Injection Protection | `stripUnknown` on all inputs (OWASP) |

---

## 🏆 Hackathon Submission

This project was built for the **AI for Bharat Hackathon** powered by AWS.

- **Track:** Student Track — AI for Learning & Developer Productivity
- **Team:** Infernyx
- **Team Lead:** Shaurya Singh
- **AI Inference:** Groq LLM API (Bedrock-equivalent, pending AWS access)
- **AWS Services Used:** DynamoDB, S3, CloudFront, CloudWatch, ElastiCache, IAM

### What makes this different from ChatGPT?

| ChatGPT | BharatLearn Dev Coach |
|---|---|
| Gives the complete solution | Never gives the solution |
| Students copy and submit | Students understand and fix |
| No curriculum awareness | Aligned to Indian university syllabi |
| Requires stable internet | Works on 2G, under 1KB per request |
| Generic global tool | Built for Indian CS students |

---

## 👥 Team

**Team Infernyx**

| Name | Role |
|---|---|
| Shaurya Singh | Team Lead, Full-Stack Development |

---

---

<div align="center">

**BharatLearn Dev Coach** · Built with ❤️ for Indian CS students

*"We are not replacing the teacher. We are scaling the best parts of one."*

[🌐 Live Demo](https://bharat-learn-frontend.vercel.app/home) · [⚙️ API](https://bharatlearn-backend.onrender.com/) · [💻 GitHub](https://github.com/shaurya-s-dev/BharatLearn-Dev-Coach-)

</div>
