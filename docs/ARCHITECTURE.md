# Architecture — Barista Training LMS

## Overview

The system is a single-product web application built entirely on Lovable (React + Lovable Cloud). All data is stored in Lovable's built-in database. AI features are powered by Google Gemini API, called server-side via Lovable's backend functions.

## System Diagram

```
┌─────────────────────────────────────────────────┐
│                  Lovable Cloud                  │
│                                                 │
│  ┌─────────────┐        ┌─────────────────────┐ │
│  │  React UI   │◄──────►│  Lovable Backend    │ │
│  │             │        │  (DB + Functions)   │ │
│  └─────────────┘        └──────────┬──────────┘ │
│                                    │             │
└────────────────────────────────────┼─────────────┘
                                     │
                          ┌──────────▼──────────┐
                          │  Google Gemini API  │
                          └─────────────────────┘
```

---

## AI Integration Details

| Feature | Input | Output |
|---|---|---|
| AI Examiner | Student answer + question + module prompt | Score, missed points, improvement tips — in student's language |
| AI Portrait | 25-question test (values, behavioral patterns, self-assessment) + prompt | Archetype, psychometrics (10 scales), SWOT, cultural fit %, role recommendations |
| AI Learning Report | Full learning history (lessons, quizzes, exams) + prompt | Strengths, risk zones, overall assessment, AI HR recommendations |
| AI HR Chatbot | User message + uploaded knowledge base (.docx) | Contextual answer based on company documents |

- Each feature uses a **separate prompt**, stored in the database
- Admin can switch Gemini model (Flash / Pro) per feature independently
- Every prompt edit is versioned — admin can roll back to any previous version

---

## Access & Expiry Logic

| Role | Access scope | Expiry |
|---|---|---|
| Candidate | 25-question assessment test only | Until admin grants intern access |
| Barista (Intern) | Full LMS | 1 month (default, configurable) |
| External Learner | 1 course only (Product Theory) | 7 days (auto-expires) |
| Admin | Everything | No expiry |

---

## Assessment Rules

**Open-ended Exams**
- 300 character minimum answer required
- Paste disabled
- AI checks for plagiarism against the reference answer — responses with >70% similarity are rejected and the student is asked to rephrase in their own words
- Graded by Gemini in real time
- 24h cooldown after 3 failed attempts
- Full answer + AI feedback stored per attempt (visible to student and admin)
- Bilingual: AI auto-detects Russian or Kazakh and responds in the same language

**Recipe Exams**
- Interactive format: student selects ingredients and specifies volumes
- AI validates correctness per drink
- Top-5 weakest drinks tracked per student profile

---

## Data Flow — Learning Path

```
Login
  │
  ▼
Theory lessons (sequential, copy-protected)
  │
  ▼
Quiz (must pass to continue)
  │
  ▼
Open-ended Exam (Gemini-graded)
  │ 3 fails → 24h cooldown
  ▼
Next module unlocks
  │
  ▼
All modules complete
  │
  ▼
Admin triggers AI Learning Report
```

## Data Flow — Candidate Hiring

```
Candidate receives access link
  │
  ▼
Completes 25-question values test
  │
  ▼
AI Portrait generated automatically on test completion
  │
  ▼
Admin compares candidates side by side
  │
  ▼
Decision → Candidate becomes Intern (access granted)
```
