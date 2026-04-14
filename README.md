# 🎓 AI-Powered LMS for Coffee Business Onboarding

> Live in production at **Seventy Company** — a 4-location coffee shop chain in Almaty, Kazakhstan.  
> An AI-powered LMS for staff onboarding, built with Lovable and Gemini.  
> **22 employees trained**, including current baristas, new hires, and management candidates.

![Lovable](https://img.shields.io/badge/Lovable-Built%20with%20Lovable-7C3AED?style=flat)
![Gemini](https://img.shields.io/badge/AI-Google%20Gemini-4285F4?style=flat&logo=google)
![React](https://img.shields.io/badge/Frontend-React-61DAFB?style=flat&logo=react&logoColor=black)
![Status](https://img.shields.io/badge/Status-Production-22c55e?style=flat)

---

## What This Is

A fully custom LMS built for Seventy Company to replace manual onboarding. The system handles structured learning, AI-graded exams, candidate psychometric profiling, and admin analytics — all in one product.

Previously, all theory was explained offline by managers individually for each new employee, with no reliable way to verify knowledge before moving to hands-on practice. Now, trainees arrive at the practical stage with full theoretical understanding — and management has data to back hiring decisions.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend & Backend | Lovable (React + Lovable Cloud) |
| AI Models | Google Gemini API (configurable per module) |
| Content Generation | NotebookLM |
| Prompt Management | Custom admin UI (editable per module) |

---

## How It Works

1. **New candidate** — receives access to the values test and AI personality profile
2. **Candidate profiling** — 25 questions answered in the app
3. **AI Candidate Portrait** — Gemini generates a full psychometric profile with archetype, SWOT, cultural fit %, and role recommendations for management
4. **Access granted** — candidate becomes an intern and gets access to the full LMS
5. **Theory** — structured lessons across 3 courses, delivered in swipeable stories format
6. **Tests & Exams** — quizzes unlock after theory; open-ended exams graded by AI in real time
7. **Next module** — unlocks only after passing current exam; 24h cooldown on failed attempts
8. **AI Learning Report** — after completing all modules, admin generates a full AI analysis: strengths, weak zones, exam history with results, recommendations
9. **Hiring decision** — management uses the portrait + report together to decide role, position, and growth path

---

## User Roles

| Role | Access |
|---|---|
| **Candidate** | Values test and candidate profile creation only — nothing else is visible |
| **Barista (Intern)** | Full LMS access (all courses, leaderboard, own profile) — learning only, with a default 1-month access period aligned with the course duration |
| **External Learner** | One course only (Product Theory), own results, auto-expires in 7 days |
| **Admin** | Everything: content management, employee management, AI reports, candidate portal, analytics, prompt editor |

---

## Key Features

### 📚 Structured Learning Flow
- 3 courses: Company Rules, Product Theory, Recipes
- Content delivered in a stories-style format (swipeable cards); copy-protected
- Sequential unlock: next topic opens only after passing current test/exam
- XP points awarded for every completed lesson and passed assessment

### 🤖 AI Examiner (Gemini)
- Open-ended exam questions graded by Gemini; minimum 300 characters, paste disabled
- AI provides instant feedback: score + what was missed + what to improve
- Bilingual support: Russian or Kazakh — AI detects language and responds in kind
- Up to 3 attempts per exam; 24h cooldown after 3 failed attempts
- Recipe exams use interactive ingredient-selection format; AI checks correctness and tracks top-5 weakest drinks per student
- Full answer + feedback history saved — visible to both student and admin

### 👤 AI Candidate Portrait (Gemini)
- Candidates complete a 25-question values test
- Gemini generates a full psychometric report:
  - Archetype (Operator / Master / Mentor / Architect)
  - Psychometrics across 10 scales
  - SWOT analysis
  - Cultural fit % with company DNA
  - Behavioral patterns
  - Tailored interview questions for the candidate
  - Onboarding recommendations
  - Best-fit role suggestions
- Side-by-side comparison of multiple candidates

### 📊 AI Learning Report (Gemini)
- Admin triggers report generation per employee
- AI analyzes: lessons completed, quiz accuracy, exam scores, weak spots
- Output: overall assessment + strengths + risk zones + recommendations
- Report history saved with timestamps

### 🏆 Gamification
- XP system, levels, streak tracking
- Leaderboard visible to all employees
- Achievements/badges (Encyclopedia, Speed Runner, Polyglot, etc.)
- Mastery Path — 5 progression levels tied to course completion (Green Bean → Tamper → Holder → Master → Espresso God)

### 💬 AI HR Chatbot
- Answers questions about company rules, culture, and processes
- Powered by Gemini with a custom knowledge base (.docx uploaded via admin)
- Quick question suggestions configurable by admin

### 🛠 Admin Panel
- Full content and employee management
- Editable AI prompts per module — no code changes needed; full version history with rollback
- Configurable Gemini model (Flash / Pro) per AI feature independently

---

## AI Prompts

The system uses separate Gemini prompts for each AI feature, all editable by admin without code changes:

- **AI Examiner** — evaluates open-ended answers, gives pedagogical feedback in student's language
- **AI Portrait** — generates psychometric candidate profile from test results
- **AI Report** — analyzes learning data and produces HR recommendations
- **AI HR Chatbot** — answers company-specific questions based on uploaded knowledge base
- **Prompt Version History** — every prompt edit is auto-saved; admins can roll back to any previous version at any time

See [`prompts/ai_examiner_example.md`](./prompts/ai_examiner_example.md) for an AI Examiner prompt structure example.  
See [`prompts/ai_portrait_prompt_template.md`](./prompts/ai_portrait_prompt_template.md) for an AI Portrait prompt structure example.

---

## Business Impact

**Before this system, onboarding at Seventy Company was fully manual:**
- Theory was explained offline by managers, individually for every new hire
- There was no reliable way to verify knowledge retention before moving to hands-on practice
- Assessing employee potential and deciding on role fit required trial and error

**Now:**
- Interns arrive at practical training with verified theoretical knowledge
- Management sees exactly where each person struggled and what they know well
- Hiring and promotion decisions are backed by AI-generated psychometric data, not gut feeling

---

## Live Usage Stats

Tracked via Lovable Analytics (last 90 days):

| Metric | Value |
|---|---|
| Visitors | 540 |
| Pageviews | 4.7k |
| Views per visit | 8.77 |
| Avg. session duration | 7m 29s |
| Bounce rate | 34% |
| Primary country | Kazakhstan (530 of 540 visitors) |
| Device split | 81.9% mobile / 18.1% desktop |

Most visited pages: `/learn` (292), `/` (288), `/leaderboard` (144), `/admin` (98)

---

## Results

| Metric | Value |
|---|---|
| Employees trained | 22 |
| Courses | 3 (55+ lessons) |
| AI-graded exams | Multiple per employee |
| Candidate profiles generated | 18 |
| External Learner | 20 |
| Locations served | 4 (Almaty, KZ) |
| Status | Production (ongoing support) |

---

## Project Status

✅ Production — live and in active use  
🔄 Ongoing maintenance: bug fixes, feature additions on request

---

## Documentation

- 📐 [`docs/ARCHITECTURE.md`](./docs/ARCHITECTURE.md) — System structure, module breakdown, and AI integration flow
- 👥 [`docs/USER_ROLES.md`](./docs/USER_ROLES.md) — Role permissions and access logic
- 🤖 [`docs/AI_FEATURES.md`](./docs/AI_FEATURES.md) — Detailed description of all AI features, prompts, and model configuration
- 🛠 [`docs/TECH_STACK.md`](./docs/TECH_STACK.md) — Full technology stack with architecture diagram

---

### 👤 Author

**Gulnaz Bakinova**

*AI Automation & Applied AI Engineer · End-to-end automation for sales / support / ops*

Let's connect!
[LinkedIn](https://www.linkedin.com/in/gulnaz-bakinova/) 

*This repository is provided for portfolio and demonstration purposes only*
