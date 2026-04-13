# Tech Stack — Barista Training LMS

## Overview

The platform is built on Lovable (React-based visual development environment) with Supabase as the backend. All AI features run through Supabase Edge Functions calling Google Gemini API.

---

## Frontend

| Technology | Role |
|---|---|
| **React** | UI framework (generated and managed via Lovable) |
| **Lovable** | Visual development environment — component building, deployment |
| **Tailwind CSS** | Styling |
| **shadcn/ui** | UI component library |

---

## Backend

| Technology | Role |
|---|---|
| **Supabase** | Backend-as-a-service: database, auth, storage, edge functions |
| **PostgreSQL** | Primary database — 33 tables |
| **Supabase Auth** | User authentication and role-based access control |
| **Supabase Storage** | File storage — 2 buckets (knowledge base docs, assets) |
| **Row Level Security (RLS)** | Data access control per user role |

---

## AI Layer

| Technology | Role |
|---|---|
| **Google Gemini 3 Flash Preview** | LLM for all 4 AI modules |
| **Supabase Edge Functions** | Serverless functions that handle AI calls and business logic |

**Model usage:** 380 calls during pilot testing with 22 employees.  
**Model selection:** Admin can switch Gemini model (Flash / Pro) oe GPT 5 per AI module independently from the admin panel.

---

## Edge Functions

Each AI feature and sensitive operation runs as a separate Edge Function:

| Function | Purpose |
|---|---|
| `check-answer` | AI Examiner — evaluates open-ended exam answers |
| `check-recipe-description` | AI Examiner — evaluates recipe description answers |
| `generate-candidate-report` | AI Portrait — generates psychometric portrait from test results |
| `enrich-candidate-report` | AI Portrait — enriches portrait with additional analysis |
| `generate-employee-report` | AI Learning Report — generates post-training report per employee |
| `chatbot` | AI HR Chatbot — processes employee questions against knowledge base |
| `parse-knowledge-base` | Parses uploaded .docx knowledge base for chatbot use |
| `create-employee` | Creates employee account with role assignment |
| `update-employee` | Updates employee profile and access settings |
| `delete-employee` | Removes employee and associated data |
| `reset-employee-password` | Admin-triggered password reset for employees |
| `reset-admin-password` | Admin password reset |
| `seed-admin` | Initial admin account setup |

---

## Database

**33 tables** covering:
- Users and roles
- Courses, modules, lessons
- Quizzes and exam questions
- Exam attempts, answers, AI feedback
- Candidate test results and AI portraits
- AI prompts and version history
- Leaderboard and gamification data (XP, levels, achievements, streaks)
- HR Chatbot knowledge base
- Admin configuration

---

## Storage

| Bucket | Contents |
|---|---|
| Knowledge base | HR Chatbot `.docx` files uploaded by admin |
| Assets | Course images and media |

---

## Architecture Flow

```
User (React frontend)
        ↓
Supabase Auth (role check)
        ↓
Supabase Edge Function
        ↓
Google Gemini API
        ↓
Response saved to PostgreSQL
        ↓
Frontend renders result
```

---

## Deployment

| Layer | Platform |
|---|---|
| Frontend | Lovable (auto-deploy on save) |
| Backend | Supabase Cloud |
| Edge Functions | Supabase Edge Runtime (Deno) |
| Database | Supabase PostgreSQL (managed) |
