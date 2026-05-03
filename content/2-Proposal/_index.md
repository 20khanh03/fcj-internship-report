---
title: "Proposal"
date: "2026-03-09"
weight: 20
chapter: false
pre: " <b> 2. </b> "
---

## Lexi - The AI Tutor That Never Judges

---

## 1. Project Overview

### Why do most English learners in Vietnam fail to speak fluently?

A familiar paradox in English language learning in Vietnam: many people master grammar and excel at written exams, yet "freeze up" when it comes to real-world communication. The problem isn't lack of ability, but rather the following barriers:

1. **Lack of a real speaking environment** — It is difficult to find partners for regular conversation.
2. **Fear of making mistakes** — Social anxiety causes learners to avoid communication, even though they know mistakes are essential for learning.
3. **Vocabulary attrition** — Without a review system, 80% of new words vanish within 30 days.
4. **Cost barriers** — High-quality tutors are often inaccessible to the majority of learners.

### What happens when learners can practice speaking without fear of judgment?

Imagine a learner with a solid grammar foundation who feels anxious and shy every time they need to speak English in public. Despite spending years and significant money on education, they cannot start a simple conversation without stress.

With an AI Tutor, they can practice speaking anytime—judgment-free and with infinite patience—at a fraction of the cost of traditional tutoring.

### What is Lexi?

**Lexi** is an AI-powered English learning platform designed to fill the gap that traditional methods often ignore: **consistent speaking practice without the fear of failure.**

Instead of trying to replace human tutors, Lexi focuses on what humans struggle to provide: 24/7 availability, unlimited patience, and a pressure-free learning environment.

**Four Core Advantages:**
- **Learn Anytime** — No scheduling required; practice even at 2 AM.
- **Personalized Feedback** — Precise suggestions tailored to the learner’s specific level and weaknesses.
- **Safe Space for Mistakes** — Zero pressure and zero judgment, helping you speak more confidently.
- **Cost-Effective** — Equivalent effectiveness to hours of tutoring at a significantly lower cost.

---

## 2. Project Goals

### Product Goals

1. Launch a functional MVP featuring the AI Tutor and vocabulary management system.
2. Onboard 50–100 active beta users to collect feedback and evaluations.
3. Complete development within a $200 AWS budget.

### Technical Goals

1. Organize and deploy a Clean Architecture backend on AWS Lambda using Serverless architecture.
2. Build the frontend using Next.js App Router with TypeScript and Shadcn/ui.
3. Integrate Amazon Bedrock for conversational AI.
4. Utilize Amazon DynamoDB for data storage.
5. Establish a CI/CD pipeline for automated testing and deployment.

### Scope and Limitations

- Prioritize core MVP functionality.
- Conversational AI should be "good enough" for use, rather than perfect.
- Ensure infrastructure stability for the development phase.
- Web-based development; mobile implementation is currently out of scope.
- Testing will focus on primary user flows.

---

## 3. Key Features

### 1. Speaking Practice with AI Tutor
- Interactive chat interface where the AI acts as a conversation partner.
- Voice Input (Amazon Transcribe) → AI Processing → Voice Output (Amazon Polly).
- Detailed feedback on grammar, pronunciation, vocabulary, and expansion tips.
- Conversation history tracking to monitor progress.

### 2. SRS-based Flashcards
- Automated vocabulary creation and review scheduling.
- SM-2 algorithm to calculate optimal review intervals.
- Tracking retention rates (Easy / Good / Hard / Again).
- Statistics: total words learned, due for review, and mastery levels.

### 3. Structured Lessons
- Content categorized by CEFR levels (A1–C2).
- Explanations for grammar, vocabulary, and real-world usage.
- Audio and video examples from native speakers.

### 4. Progress Dashboard
- Stats: study hours, accumulated vocabulary, and retention rates.
- Streaks — consecutive days of learning.
- Achievement badges based on learning milestones.
- Progress charts over time.

---

## 4. Solution Architecture

### Tech Stack & Rationale

The stack was chosen based on one criterion: **best fit for an 8-week solo developer timeline.**

| Layer | Technology | Rationale |
| :--- | :--- | :--- |
| **Frontend** | Next.js + TypeScript | Balances speed with type safety; App Router simplifies routing and APIs. |
| **Backend** | Python 3.12 + AWS Lambda | Serverless eliminates infra management; Python offers powerful SDKs. |
| **AI** | Amazon Bedrock Nova Lite | Conversational AI without ML expertise; 90% cheaper than custom models. |
| **Voice** | Amazon Transcribe + Polly | WebSocket streaming for natural voice experience; managed services reduce complexity. |
| **Database** | DynamoDB (Single-table) | Auto-scales with Lambda; predictable performance with pay-per-use pricing. |
| **Auth** | Amazon Cognito | Managed authentication with OAuth integration; no need to build from scratch. |
| **Deployment** | Amplify + SAM | Decoupled pipeline — frontend and backend can iterate independently. |

---

## 5. Timeline

### Phase 1 — Preparation (Weeks 1–2)
* **Week 1:** Master AWS Serverless, Lambda, and DynamoDB. Learn Bedrock, Transcribe, and Polly integrations.
* **Week 2:** Study Clean Architecture in Python. Design database schema and API specifications.

### Phase 2 — Development (Weeks 3–8)
* **Weeks 3–4 (Sprint 1):** Backend (Auth, API, DB) and Frontend (UI components, layout).
* **Weeks 5–6 (Sprint 2):** AI Tutor integration (Bedrock) and Flashcard system (SRS).
* **Week 7 (Sprint 3):** Voice integration (Transcribe + Polly) and Dashboard analytics.
* **Week 8 (Sprint 4):** Testing, optimization, and final MVP deployment.

---

## 6. Budget

### Monthly Operating Cost Estimates

| Scenario | Estimated Cost/Month | Key Drivers |
| :--- | :--- | :--- |
| **Dev & Testing (100 users)** | **$12.03** | Heavy use of Free Tier; minimal AI tokens. |
| **Moderate Growth (500 users)**| **$59.65** | Increased S3 storage and AI/ML service usage. |
| **High Growth (1,000+ users)** | **$119.30** | Scaling AI/ML services and higher data throughput. |

**Budget Allocation ($200):**
* **Months 1-2 (Dev):** $50
* **Month 3 (Launch):** $50
* **Months 4-6 (Growth):** $100

---

## 7. Risk Assessment

- **Technical:** Potential AI latency (>2s). *Mitigation:* Use response streaming and prompt optimization.
- **Financial:** Risk of exceeding AWS budget. *Mitigation:* Daily monitoring via AWS Budgets and per-user quotas.
- **Product:** AI response quality. *Mitigation:* Prompt engineering loops and A/B testing.

---

## 8. Success Indicators

### Technical
- ✅ Functional MVP with all core features working.
- ✅ Response time < 2 seconds.
- ✅ 99%+ Uptime.

### User Metrics
- ✅ 100+ Beta users.
- ✅ 4.0+/5.0 User rating.
- ✅ Daily active rate ≥ 50%.

---

## 9. Conclusion

Lexi addresses the exact problem traditional methods miss: **the lack of a safe and frequent speaking environment.** By utilizing AWS Serverless and managed AI services, Lexi provides a scalable, cost-effective solution that helps learners finally overcome the barrier of speaking.
