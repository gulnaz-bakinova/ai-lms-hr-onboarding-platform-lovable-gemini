# Security & Privacy Notice

## Confidentiality

This repository documents a production system built for a real coffee business.  
All sensitive and confidential information has been intentionally excluded or anonymized.

**What has been removed or masked:**

- Company-specific content (course materials, internal rules, recipes, standards)
- Employee names and personal data — masked in all screenshots
- Candidate names and test results
- Company-specific values, thresholds, and cultural criteria used in AI prompts
- AI prompts in `prompts/` are sanitized templates — not the production versions stored in the database

---

## Credentials & Environment Variables

No API keys, secrets, or credentials are stored in this repository.

All sensitive configuration is managed via environment variables in Supabase:

- `GEMINI_API_KEY` — Google Gemini API key
- `SUPABASE_SERVICE_ROLE_KEY` — Supabase service role key
- Any other runtime secrets

These are set directly in the Supabase project settings and never committed to code.

---

## Data Privacy

The platform was tested with 22 real employees during a paid pilot.  
No personal data from that pilot appears in this repository.  
Screenshots included in `assets/screenshots/` have all names and personal identifiers masked.

---

## Responsible Disclosure

This is a portfolio repository — the production system is not publicly accessible.  
If you notice any sensitive information that was accidentally included, please contact the author directly.
