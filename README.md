# BharatLearn Dev Coach v2.0

AI-powered CS learning platform — single codebase, one command to run.

## Quick Start

```bash
# 1. Install everything
npm run setup

# 2. Configure backend secrets
cp backend/.env.example backend/.env
# Fill in: AWS credentials, Google OAuth, SESSION_SECRET

# 3. Run both servers
npm run dev
```

Open → **http://localhost:3001**

---

## What's Running

| Service  | URL                      | Purpose              |
|----------|--------------------------|----------------------|
| Frontend | http://localhost:3001    | Next.js React UI     |
| Backend  | http://localhost:3000    | Express API (proxied)|

The frontend proxies `/api/*` and `/auth/*` to the backend automatically — **you only open one URL**.

---

## Features

| Page          | Route         | What it does                              |
|---------------|---------------|-------------------------------------------|
| Dashboard     | /dashboard    | Charts: streak, mastery, weak areas       |
| Learning Plan | /learning     | Upload syllabus → 24-week roadmap         |
| Debug Code    | /debug        | Paste code → Socratic hints (no solutions)|
| Quiz          | /quiz         | Topic → 10 questions (MCQ/Short/Coding)   |
| Viva Predictor| /viva         | Upload code → 20 viva questions           |
| Settings      | /settings     | Profile, language, Google login           |

---

## Environment Variables (backend/.env)

```env
PORT=3000
NODE_ENV=development
FRONTEND_URL=http://localhost:3001
SESSION_SECRET=<64-char-random-string>

# AWS Bedrock
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=<your-key>
AWS_SECRET_ACCESS_KEY=<your-secret>
BEDROCK_MODEL_ID=anthropic.claude-3-sonnet-20240229-v1:0

# Google OAuth (console.cloud.google.com)
GOOGLE_CLIENT_ID=<client-id>.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=<secret>
```

---

## Google OAuth Setup (5 min)

1. Go to https://console.cloud.google.com/apis/credentials
2. Create OAuth 2.0 Client ID → Web application
3. Add Authorised redirect URI: `http://localhost:3000/auth/google/callback`
4. Copy Client ID and Secret → paste in `backend/.env`

---

## Security Measures

- **Helmet** – 15+ HTTP security headers
- **CORS** – Restricted to frontend origin only
- **Rate Limiting** – Separate limits for AI (10/min), auth (20/15min), general (60/min)
- **Input Validation** – Joi schema validation on all endpoints
- **Session Security** – httpOnly + sameSite cookies, server-side session
- **No secrets in frontend** – All AI keys stay in backend .env
- **Payload limits** – 32kb JSON, 10MB file uploads
- **OWASP** – Injection protection via stripUnknown on all inputs

---

## Project Structure

```
bharatlearn/
├── package.json          ← root: runs both servers with concurrently
├── backend/
│   ├── server.js         ← SINGLE FILE: all routes, auth, AI, security
│   ├── package.json
│   └── .env.example
└── frontend/
    ├── src/
    │   ├── app/
    │   │   ├── layout.tsx
    │   │   ├── dashboard/page.tsx
    │   │   ├── learning/page.tsx
    │   │   ├── debug/page.tsx
    │   │   ├── quiz/page.tsx
    │   │   ├── viva/page.tsx
    │   │   └── settings/page.tsx
    │   └── components/
    │       └── Sidebar.tsx
    ├── next.config.ts    ← proxies /api/* → backend
    └── package.json
```
