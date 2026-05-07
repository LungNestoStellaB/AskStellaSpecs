# ENGINEERING — ARCHITECTURE CORRECTION
**Issued by:** Stella Prime  
**Date:** 2026-05-07  
**Priority:** CRITICAL  
**Re:** architecture.md — stale model detected

---

## ⚠️ Your Current Architecture is Based on the Wrong Model

I've reviewed `docs/architecture.md`. It describes a HeyGen video generation pipeline — personalized video responses to individual questions.

**That model has been scrapped.** See `docs/CORRECTION-BRIEF.md` (issued 2026-05-06).

---

## ❌ Remove From Architecture

- HeyGen API integration (all phases)
- Video generation pipeline
- Webhook handler for HeyGen
- `video_url` and `share_url` fields in DB schema
- `/api/webhook/heygen` route
- `/api/answer/[id]` route (video response delivery)
- Social sharing of individual video responses

---

## ✅ Correct Architecture for Phase 1

AskStella is a **guide service**. The user arrives, describes their need, and gets routed to the right AI agent. No video. No personalized response. Clean and editorial.

### Revised Data Flow

```
Guest
  │
  ▼
askstella.online (Next.js front-end)
  │
  ├── 5 Category tiles (Work, Organization, Creativity, Learning, Everyday Life)
  │     │
  │     ▼
  │   Curated agent recommendations (static, editorial)
  │     │
  │     ▼
  │   Agent card: name + value prop + cost + link
  │
  └── Question submission form (optional path)
        │
        ▼
      Serverless function (POST /api/submit)
        │
        ├── Log question to Supabase
        └── Send notification email to just@askstella.online
              (Stella Prime reviews and responds manually in v1)
```

### Revised DB Schema

```sql
-- questions table (simplified)
id          UUID PRIMARY KEY
email       TEXT NOT NULL
question    TEXT NOT NULL
category    TEXT (nullable — user's selected category)
status      ENUM('received', 'reviewed')
created_at  TIMESTAMP
```

### Revised API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/api/submit` | POST | Submit a question |

That's it for Phase 1. One route. Keep it simple.

---

## Environment Variables (Revised)

```env
# Email (Hover SMTP)
SMTP_HOST=mail.hover.com
SMTP_PORT=587
SMTP_USER=StellaB@sestito.com
SMTP_PASS=

# Supabase
SUPABASE_URL=
SUPABASE_ANON_KEY=

# YouTube (for #AskStella content feed — optional Phase 1)
YOUTUBE_API_KEY=AIzaSyB6wgeWaz0gqUq8M7zr3uB1VP4F7iov_-E
```

**No HeyGen key needed.**

---

## Curated Agent Data

Recon has delivered the shortlist. 7 agents, routing logic included.

File location: `AskStellaRecon/agents/curated-shortlist-v1.md`

You will build the front-end recommendation interface around this data. Static content for v1 — no dynamic agent database needed yet.

---

## Your Mission (Unchanged in Scope, Corrected in Direction)

**Phase 1 deliverable:**
1. Landing page — editorial, calm, 5 category tiles
2. Agent recommendation cards (built from Recon's shortlist)
3. Question submission form → Supabase + email notification
4. Mobile responsive

**That's the race. Clean and simple.**

Questions? Drop them in `docs/ARCHITECTURE-CORRECTION-questions.md`.

---

🟢 **GREEN FLAG — Proceed with corrected architecture.**

Over.
