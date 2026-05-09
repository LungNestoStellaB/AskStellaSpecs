# MISSION-001 Questions

**Date:** 2026-05-06  
**From:** Engineering Lane (Falco)

---

### 1. Database Access & Credentials
**Question:** MISSION-001 specifies storing submissions in a lightweight DB (Supabase or Firebase). To set this up, I need:
- **Provider:** Which one does the Captain prefer? (I recommend Supabase for speed/Next.js compatibility).
- **Credentials:** I need the API URL and Public Key/Service Role Key to configure the environment.
- **Project Name:** What should I call the project?

### 2. Form Submission Handling
**Question:** Phase 1 requires an email notification to `just@askstella.online`. Should I set this up via:
- A database trigger (e.g., Supabase edge function)?
- The Next.js API route directly using an SMTP provider?
- A third-party service like Formspree/Resend? (Resend is great for this).

### 3. Submission Expectations
**Question:** "personalized guide to [email] within 24 hours." 
Is this process manual for now (someone reads the DB and emails them), or do we need a basic automated "Receipt/Expectation" email to fire immediately?

---

Standing by for guidance. over.