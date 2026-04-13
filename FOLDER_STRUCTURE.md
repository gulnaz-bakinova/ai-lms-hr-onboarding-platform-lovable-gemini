# Repository Structure

```
barista-lms/
│
├── README.md                        # Project overview, features, pilot results
├── SECURITY.md                      # Confidentiality notice, credential policy
│
├── docs/
│   ├── ARCHITECTURE.md              # System architecture, roles, access logic
│   ├── USER_ROLES.md                # 4 roles: Candidate, Intern, External, Admin
│   ├── AI_FEATURES.md               # All 4 AI modules in detail
│   └── TECH_STACK.md                # Frontend, backend, AI layer, edge functions
│
├── prompts/
│   ├── ai_examiner_prompt.md        # Live prompt — AI Examiner (answer evaluation)
│   └── ai_portrait_prompt_template.md  # Sanitized template — AI Portrait system prompt
│
└── assets/
    ├── 00_architecture_flow.png     # System architecture diagram
    ├── 01_course-overview.png       # Course catalogue view
    ├── 02_topic-view.png            # Topic breakdown inside a course
    ├── 03_lesson-view.png           # Lesson content screen
    ├── 04_exam-question.png         # AI Examiner — open-ended question
    ├── 05_exam-feedback.png         # AI Examiner — feedback on answer
    ├── 06_exam-recipes.png          # Recipe knowledge exam
    ├── 07_exam-recipes-feedback.png # Recipe exam — AI feedback
    ├── 08_dashboard-leaderboard.png # Employee dashboard with leaderboard
    ├── 09_employee-profile.png      # Employee profile page (pt. 1)
    ├── 10_employee-profile_2.png    # Employee profile page (pt. 2)
    ├── 11_chatbot.png               # AI Assistant chatbot
    ├── 12_admin-panel.png           # Admin panel — general view
    ├── 13_admin-panel-ai-hr.png     # Admin panel — AI HR module
    ├── 14_edit-content.png          # Content editor interface
    ├── 15_admin-prompt-editor.png   # Live prompt editor in admin
    ├── 16_exam-history.png          # Exam history and attempts log
    ├── 17_ai-report.png             # AI-generated employee report
    ├── 18_ai-portrait-archetypes.png    # AI Portrait — archetype analysis
    ├── 19_ai-portrait-cultural-fit.png  # AI Portrait — cultural fit scoring
    └── 20_ai-portrait-swot.png          # AI Portrait — SWOT breakdown
```

---

## File Index

| File | Location | Purpose |
|---|---|---|
| `README.md` | root | First impression — what the project is, what it does, pilot results |
| `SECURITY.md` | root | Confidentiality and credential policy |
| `ARCHITECTURE.md` | docs/ | Full system overview: modules, roles, access rules, data flow |
| `USER_ROLES.md` | docs/ | Detailed breakdown of all 4 roles with permissions |
| `AI_FEATURES.md` | docs/ | Deep dive into all 4 AI modules with edge functions and design decisions |
| `TECH_STACK.md` | docs/ | Technology choices with architecture flow diagram |
| `ai_examiner_prompt.md` | prompts/ | Production prompt with output format and design rationale |
| `ai_portrait_prompt_template.md` | prompts/ | Sanitized template showing prompt architecture for AI Portrait |
| `assets/` | root | 21 UI screenshots with all personal data masked |
