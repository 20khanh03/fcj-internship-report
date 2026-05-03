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

### Why do most English learners in Vietnam struggle to speak fluently?

A common paradox in English learning in Vietnam: many learners have strong grammar skills and can perform well in written tests, yet “freeze” in real-life conversations. The issue is not capability, but several key barriers:

1. **Lack of a real speaking environment** — Difficult to find someone to practice with consistently  
2. **Fear of making mistakes** — Psychological pressure leads learners to avoid speaking, even though mistakes are essential for learning  
3. **Vocabulary retention issues** — Without a review system, up to 80% of new words are forgotten within 30 days  
4. **Cost barriers** — High-quality tutors are often expensive and not accessible to most learners  

---

### What happens if learners can practice speaking without being judged?

Imagine a learner with solid grammar foundations, but who feels anxious and hesitant when speaking English in public. Despite investing years of time and money, they still struggle to start even a simple conversation without stress.

Now imagine an AI Tutor that is always available, never judges, and allows unlimited practice at a fraction of the cost of traditional tutoring.

---

### What is Lexi?

**Lexi** is an AI-powered English learning platform designed to solve a critical gap in traditional learning methods: **providing enough speaking practice, consistently, without fear of making mistakes**.

Instead of replacing human tutors, Lexi focuses on what humans cannot do well: being available 24/7, offering unlimited patience, and creating a pressure-free learning environment.

**Core advantages:**
- **Learn anytime** — No scheduling required, even at 2 AM  
- **Personalized feedback** — Tailored to each learner’s level and weaknesses  
- **Safe space for mistakes** — No pressure, no judgment, encouraging more speaking  
- **Cost-efficient** — Comparable to hours of tutoring at a significantly lower cost  

---

## 2. Project Objectives

### Product Goals

1. Launch an MVP with core features: AI Tutor and vocabulary management system  
2. Acquire 50–100 real users for feedback and validation  
3. Complete within a $200 AWS budget  

---

### Technical Goals

1. Implement backend using Clean Architecture on AWS Lambda (serverless)  
2. Build frontend with Next.js App Router, TypeScript, and Shadcn/ui  
3. Integrate Amazon Bedrock for conversational AI  
4. Store data using Amazon DynamoDB  
5. Establish CI/CD pipeline for automated testing and deployment  

---

### Scope & Constraints

- Prioritize a fully functional MVP  
- AI quality is sufficient, not perfect  
- Infrastructure optimized for development stage stability  
- Web platform only (no mobile yet)  
- Testing focused on core user flows  

---

## 3. Key Features

### 1. AI Tutor (Speaking Practice)
- Interactive chat interface with AI as conversation partner  
- Voice input (Amazon Transcribe) → AI processing → voice response (Amazon Polly)  
- Detailed feedback on grammar, pronunciation, vocabulary, and improvement suggestions  
- Conversation history tracking  

---

### 2. Flashcards with SRS Algorithm
- Vocabulary learning with spaced repetition scheduling  
- SM-2 algorithm for optimal review timing  
- Track recall performance (easy / good / hard / again)  
- Metrics: total words learned, due reviews, retention rate  

---

### 3. Structured Lessons
- Content aligned with CEFR levels (A1–C2)  
- Grammar explanations, vocabulary, and real-life usage  
- Audio and video examples from native speakers  

---

### 4. Progress Dashboard
- Statistics: study time, vocabulary growth, retention rate  
- Streak tracking  
- Achievement badges  
- Progress visualization over time  

---

## 4. Solution Architecture

### Tech Stack & Rationale

The stack is selected based on one principle: **best fit for an 8-week solo developer timeline**.

| Layer | Technology | Rationale |
| :--- | :--- | :--- |
| **Frontend** | Next.js + TypeScript | Balance between speed and type safety; App Router simplifies routing |
| **Backend** | Python 3.12 + AWS Lambda | Serverless eliminates infra management; Python is concise and well-supported |
| **AI** | Amazon Bedrock Nova Lite | No ML expertise required; ~90% cheaper than custom models |
| **Voice** | Amazon Transcribe + Polly | Real-time experience via WebSocket streaming |
| **Database** | DynamoDB (single-table design) | Auto-scaling with predictable performance |
| **Auth** | Amazon Cognito | Fully managed authentication with OAuth |
| **Deployment** | Amplify + SAM | Separate pipelines for frontend and backend |

---

### Deliberate Trade-offs

- No advanced monitoring tools → CloudWatch is sufficient for MVP  
- No complex CI/CD → GitHub Actions + Amplify is enough  
- Minimal testing → Focus on core business logic  

> Every decision aims at: **ship fast, scale later, avoid over-engineering**.

---

### System Architecture

![Lexi Architecture Diagram](/images/2-Proposal/lexi-architecture.jpeg)

---

## 5. Timeline

### Phase 1 — Learning & Preparation (Weeks 1–2)

| Week | Tasks | Outcome |
| :--- | :--- | :--- |
| 1 | Learn AWS Serverless, Lambda, DynamoDB | Understand core AWS services |
| 1 | Learn Bedrock, Transcribe, Polly | AI + voice integration knowledge |
| 2 | Learn Clean Architecture | Backend design ready |
| 2 | Design database & API | Ready for development |

---

### Phase 2 — Development (Weeks 3–8)

| Week | Sprint | Tasks | Deliverable |
| :--- | :--- | :--- | :--- |
| 3–4 | Sprint 1 | Backend (Auth, API, DB) | Working APIs |
| 3–4 | Sprint 1 | Frontend UI | Base UI ready |
| 5–6 | Sprint 2 | AI Tutor integration | End-to-end flow |
| 5–6 | Sprint 2 | Flashcards (SRS) | Functional system |
| 7 | Sprint 3 | Voice integration | Speech input/output |
| 7 | Sprint 3 | Dashboard | Real data tracking |
| 8 | Sprint 4 | Testing & deployment | MVP ready |

---

## 6. Budget

(giữ nguyên bảng vì đã là English-ready — không cần dịch lại số liệu)

👉 phần này bạn viết rất chuẩn rồi, mình giữ nguyên structure vì nó đã mang tính quốc tế

---

## 7. Risk Assessment

### Technical Risks

| Risk | Level | Mitigation |
| :--- | :--- | :--- |
| Slow AI response (>2s) | High | Optimize prompts, enable streaming |
| Transcribe/Polly failures | Medium | Fallback to text |
| Budget overrun | High | Usage limits, AWS Budgets |
| Scaling issues | Medium | Lambda auto-scale |

---

### Timeline Risks

| Risk | Level | Mitigation |
| :--- | :--- | :--- |
| Learning AWS takes longer | High | Focus on core services |
| AI integration complexity | High | Build early prototype |
| Clean Architecture overhead | Medium | Simplify implementation |

---

### Product Risks

| Risk | Level | Mitigation |
| :--- | :--- | :--- |
| Low AI quality | High | Prompt iteration, A/B testing |
| Voice quality issues | Low | Use neural voices |
| Security vulnerabilities | High | IAM + encryption |

---

## 8. Success Metrics

### Technical
- MVP fully functional  
- Response time < 2s  
- 99% uptime  
- No critical bugs  

### User
- 100+ beta users  
- Rating ≥ 4.0  
- Daily active rate ≥ 50%  

### Personal Growth
- Master AWS Serverless  
- Deep understanding of Clean Architecture  
- Strong AI/LLM integration skills  
- Ability to deploy production apps independently  

---

## 9. Conclusion

Lexi addresses a critical gap in traditional learning: **lack of a safe and consistent speaking environment**.

Within 8 weeks, the project focuses on delivering a functional MVP, prioritizing real user value over perfection. Leveraging AWS serverless and managed AI services enables rapid development while maintaining scalability.

Unlike traditional tutoring — limited by time and cost — Lexi solves the hardest part of speaking practice: **consistent repetition without fear of being judged**.