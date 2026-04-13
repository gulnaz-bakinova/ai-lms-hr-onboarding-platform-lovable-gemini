# AI Features — Barista Training LMS

## Overview

The platform uses Google Gemini across 4 separate AI modules. Each module has its own prompt, model configuration, and admin controls.

All prompts are editable from the admin panel without code changes. Every prompt update is versioned automatically, so previous versions can be restored at any time.

---

## 1. AI Examiner

Used in open-ended exams during training.

**What it does:**
- Evaluates free-text student answers in real time
- Returns a score, missed points, and improvement guidance
- Detects whether the answer is written in Russian or Kazakh and responds in the same language
- Checks plagiarism against the reference answer; responses with more than 70% similarity are rejected

**Exam rules:**
- Minimum 300 characters required
- Paste is disabled
- 24h cooldown after 3 failed attempts
- Every attempt is stored: student answer + AI feedback + timestamp

**Why it matters:**
It replaces subjective manual checking and ensures that employees explain theory in their own words before moving to practice.

---

## 2. AI Portrait

Used for candidates before they receive training access.

**Trigger:**
Generated automatically after completion of the 25-question assessment test.

**What it analyzes:**
- Values
- Behavioral patterns
- Self-assessment
- Work attitude and motivation signals

**Output includes:**
- Primary and secondary archetype (Operator / Master / Mentor / Architect)
- Psychometry across 10 scales:
  - Empathy
  - Toxicity
  - Values Alignment
  - Responsibility
  - Learnability
  - Loyalty
  - Discipline
  - Customer Orientation
  - Self-Reflection
  - Stress Resilience
- Behavioral patterns
- Motivation type
- Maturity level
- Burnout risk
- Adaptation forecast
- Cultural fit with Seventy Company DNA
- SWOT analysis
- Tailored interview questions
- Onboarding recommendations
- Best-fit role recommendations

**Why it matters:**
It helps management evaluate not just whether a person wants the job, but how they think, adapt, and fit the company culture.

---

## 3. AI Learning Report

**Trigger:**
Generated manually by admin for any employee at any point in the process.

**What it analyzes:**
- Lesson completion
- Quiz accuracy
- Exam scores
- Repeated mistakes
- Weak topics and weak drinks
- Overall learning consistency

**Output includes:**
- Overall assessment
- Strengths
- Risk zones
- Learning gaps
- Practical readiness signals
- Recommendations for next development step

**Why it matters:**
It gives management a structured post-training view of each employee and supports decisions about growth path and role placement.

---

## 4. AI HR Chatbot

Built into the employee profile.

**What it does:**
- Answers questions about company rules, culture, and internal processes
- Uses an admin-uploaded `.docx` knowledge base
- Shows configurable quick question suggestions

**Why it matters:**
It reduces repetitive manager explanations and gives employees a self-serve way to clarify company information.

---

## Admin Controls

Admins can manage AI behavior without touching code.

**Available controls:**
- Edit prompt text for each AI module
- Store prompt version history automatically
- Roll back to any previous prompt version
- Choose Gemini or GPT model per module independently

This makes the system adaptable: prompts can evolve with the business, while old working versions remain recoverable.
