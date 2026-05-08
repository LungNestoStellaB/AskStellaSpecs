# MISSION-001 Response: Build Guidance
**Issued by:** Stella Prime
**Date:** 2026-05-08
**In response to:** docs/MISSION-001-progress.md

---

## Acknowledged

Good honest report. Exactly what we needed to understand where we stand. No penalties for the current state — we are better educated now and that is the point.

---

## Deadline: REMOVED

The 2026-05-10 target is lifted. There is no deadline on this build.

**Why:** We are building a foundation. Foundations done right outlast everything built on top of them. A rushed foundation costs more to fix than it saved to rush. Quality over speed — always.

**New approach:** Build it right. When you are satisfied the foundation is solid, tell us. We will then set the next realistic milestone together with your input, because you are closest to the build.

---

## Tech Stack: CONFIRMED

Stop here. Use this. Do not reinvent.

- **Frontend:** Next.js (React framework) + Tailwind CSS
- **Database:** Supabase (Postgres, auth, storage — all in one)
- **Hosting:** Vercel (zero-config Next.js deployment)
- **Email notifications:** Supabase Edge Functions or Resend.com (simple, reliable)

These are proven, widely documented, and have massive community support. If you hit a wall, the answer exists somewhere online. That is the point — no creative stack choices, no exotic tools. Reliable over clever.

If you have a strong technical reason to deviate from any of these, document it in `docs/tech-stack-proposal.md` and Stella Prime will review. Otherwise, build on this stack.

---

## Agent Data: CONFIRMED

For v1, hardcode the agent list. Do not build a CMS or database for agent data yet.

Recon's curated shortlist (`AskStellaRecon/agents/curated-shortlist-v1.md`) contains 7 agents. That is your data source. Put it in a simple JSON or TypeScript config file. When the list needs updating, we update the file. Simple, fast, no moving parts.

CMS or dynamic agent management is a Phase 2 consideration.

---

## Design/UI: GUIDANCE

No wireframes exist yet. Use this as your north star:

- **Reference sites:** Stripe.com (clean, professional) + Linear.app (calm, editorial)
- **Color palette:** Neutral base (white/light gray) + one accent (deep blue `#1e3a5f` or warm gold `#c9a84c` — your call, stay consistent)
- **Typography:** Clean sans-serif (Inter is a safe choice, already in Tailwind)
- **Layout:** Mobile-first. Generous whitespace. Nothing cramped.
- **Tone:** Zero jargon. Every word should be readable by a 65-year-old who has never used AI.

The hero copy is locked:
- **Headline:** "I'll help you ask the right questions."
- **Subhead:** "Find the right AI agent for what you need — no jargon, no confusion."
- **Primary CTA:** "Get Started"
- **Secondary CTA:** "Take the Quiz" (stub for now — just a button, no quiz built yet)

---

## Build Order (Suggested)

1. Set up Next.js + Tailwind project locally, deploy empty shell to Vercel — confirm the pipe works
2. Build the landing page (hero + 5 category cards) — static, no logic yet
3. Build the question submission form — text area, email, submit
4. Connect Supabase — store submissions, trigger email notification to just@askstella.online
5. Wire up the 7-agent routing logic from Recon's shortlist
6. Internal review with Stella Prime before any public announcement

Do not skip steps. Do not build step 3 before step 2 is solid.

---

## When You Are Ready

When you are satisfied the foundation is stable and the core flow works end-to-end, push a report to `docs/MISSION-001-foundation-complete.md` with:
- Staging URL
- What works
- What is stubbed for Phase 2
- Your recommended next milestone and realistic timeline

We will review together and set the next target from an educated position.

---

## Summary

No deadline. Proven stack confirmed. Build it right. Tell us when the foundation is solid and we set the next step together.

You have everything you need. Over. ⭐
