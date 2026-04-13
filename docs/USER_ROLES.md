# User Roles — Barista Training LMS

## Role Overview

The system has 4 roles. Access is assigned by admin and determines what each user can see and do.

| Role | Who it's for | Access scope | Expiry |
|---|---|---|---|
| **Candidate** | Job applicants | Assessment test only | Until admin grants intern access |
| **Barista (Intern)** | New hires and current staff | Full LMS | 1 month (default, configurable) |
| **External Learner** | Staff from partner locations or external trainees | 1 course only (Product Theory) | 7 days (auto-expires) |
| **Admin** | Management | Everything | No expiry |

---

## Candidate

Receives an access link before being hired. Cannot see the LMS.

**Can:**
- Complete the 25-question assessment test

**Cannot:**
- View their own submitted answers
- Access any courses, lessons, or exams
- See the leaderboard or other profiles
- See any other part of the app
- Re-entry with the same phone number is blocked after 2 hours from registration — prevents sharing test content with other candidates

**Session timer:**
- The assessment test must be completed within a **2-hour window** from the moment the session starts
- If time runs out before the test is finished, the attempt is saved as **Incomplete** (`is_complete: false`)
- The result screen shows partial progress (e.g. "Answered 5 of 25") — no AI Portrait is generated
- Admin can reset the session manually via the ↻ button and issue a new link

On test completion, an AI Portrait is generated automatically and becomes visible to admin.  
Admin reviews the portrait and decides whether to grant intern access.

---

## Barista (Intern)

Standard role for all staff going through onboarding.

**Can:**
- Access all 3 courses (Company Rules, Product Theory, Recipes)
- Complete lessons, quizzes, and exams
- View their own profile: XP, level, streaks, achievements, exam history with AI feedback
- View the leaderboard
- Use the AI HR Chatbot

**Mastery Path:**

Progress through 5 levels as courses are completed:

| Level | Title | Unlocked by |
|---|---|---|
| 1 | Green Bean | Starting point — access granted |
| 2 | Tamper | Complete Company Rules course |
| 3 | Holder | Complete Product Theory course |
| 4 | Master | Complete Recipes course |
| 5 | Espresso God | All courses completed |

**Cannot:**
- Access admin panel
- View other employees' exam answers or AI reports
- Manage content or users

**Exam timer:**
- Each open-ended exam question has a countdown timer
- If the timer runs out before the answer is submitted, the exam is force-completed with a result of **0%**
- The result screen is shown immediately with a score of 0%, and this attempt counts toward the **daily attempt limit**
- The timer does not pause — an expired timer is treated as a failed attempt, not a skipped one

---

## External Learner

For staff from other locations or external trainees who need product knowledge only.

**Can:**
- Access 1 course (Product Theory)
- Complete lessons and quizzes within that course
- View their own results

**Cannot:**
- Access Company Rules or Recipes courses
- See the leaderboard or other profiles
- Use the AI HR Chatbot

Access expires automatically after 7 days.

---

## Admin

Full access to all system functionality.

**Can:**
- Manage all content: courses, modules, lessons, quizzes, exams
- Manage all users: assign roles, set access duration, revoke access, password reset
- View any employee's full learning history, exam answers, and AI feedback
- Generate and view AI Learning Reports per employee at any point in the process
- Access the Candidate portal: view AI portraits, compare candidates side by side and print the report in PDF
- Edit AI prompts for all features (Examiner, Portrait, Report, Chatbot)
- Roll back any prompt to a previous version
- Switch Gemini model (Flash / Pro) or GPT-5 model per AI feature independently
- Upload and update the HR Chatbot knowledge base (.docx)
- View platform analytics
