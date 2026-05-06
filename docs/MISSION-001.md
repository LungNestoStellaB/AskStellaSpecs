# MISSION 001: Front Page Build
**Issued by:** Stella Prime  
**Date:** 2026-05-06  
**Priority:** HIGH  
**Status:** ACTIVE

---

## Mission Objective

Build the AskStella front page (landing page) and question submission flow.

This is Phase 1 of the guest-facing experience. Clean, calm, editorial. Guide-first, quiz opt-in. No hype, no jargon.

---

## Core Requirements

### 1. Landing Page

**Hero Section:**
- Headline: "I'll help you ask the right questions."
- Subhead: Brief explanation of what AskStella does (the agent's agent)
- Primary CTA: "Get Started" (leads to question submission)
- Secondary CTA: "Take the Quiz" (opt-in interactive assessment)

**5 Categories (Front Page):**
- Work
- Organization
- Creativity
- Learning
- Everyday Life

Each category should be clickable and lead to a filtered view or guide page (Phase 2 — stub for now).

**Tone & Style:**
- Editorial, calm, disarming
- Professional but not corporate
- Accessible to ordinary people (45-65+ demographic)
- Clean typography, generous whitespace
- Mobile-first responsive design

### 2. Question Submission Flow

**Simple form:**
- "What do you need help with?" (text area, 500 char max)
- Optional: Category selection (dropdown)
- Email address (for response delivery)
- Submit button

**Confirmation:**
- "Thanks! We'll send your personalized guide to [email] within 24 hours."
- Set expectations clearly

**Backend:**
- Store submissions in lightweight DB (Supabase or Firebase)
- Email notification to just@askstella.online when new submission arrives
- No HeyGen integration yet (Phase 2)

---

## Tech Stack

**Recommended:**
- Next.js (React framework)
- Tailwind CSS (styling)
- Supabase or Firebase (database + auth if needed later)
- Vercel or Netlify (hosting)

**You own HOW.** If you have a better stack recommendation, document it in `docs/tech-stack-proposal.md` and I'll review.

---

## Deliverables

1. **Working front page** (deployed to staging URL)
2. **Question submission flow** (functional, storing to DB)
3. **Documentation:**
   - `docs/setup-instructions.md` (how to run locally)
   - `docs/deployment-guide.md` (how to deploy)
   - `docs/database-schema.md` (submission structure)

---

## Design References

**Vibe:**
- Stripe.com (clean, professional, not flashy)
- Linear.app (calm, editorial, generous whitespace)
- NOT: Flashy SaaS landing pages with animations and hype

**Color palette:**
- Neutral base (whites, grays)
- One accent color (suggest: deep blue or warm gold)
- Keep it simple

---

## Timeline

**Target completion:** 2026-05-10  
**Check-in:** 2026-05-08 (progress update in `docs/MISSION-001-progress.md`)

---

## Chain of Command

- **Engineering owns:** HOW (tech stack, implementation, deployment)
- **Stella owns:** WHAT (requirements, content, strategic fit)
- **Captain owns:** WHY (business decisions, launch timing)

Questions? Drop them in `docs/MISSION-001-questions.md` and I'll respond.

---

## Phase 2 Preview (Not in scope yet)

- HeyGen integration (video response generation)
- Email delivery automation
- Category guide pages
- Interactive quiz build-out

Focus on Phase 1 first. Nail the foundation.

---

**Status:** 🟢 GREEN — Deploy when Ops clears you.

Over.
