# AskStella Specs

**Technical specifications for the AskStella platform.**

This repo is the build layer. Engineering Lane works from here. All technical specs, architecture docs, integration details, and UX flows live here.

---

## Chain of Command

| Role | Owner | Owns |
|------|-------|------|
| **Why** | Captain (Lung Nesto) | Strategic direction, final approval |
| **What** | Stella | User experience, flow, messaging, decisions |
| **How** | Engineering Lane | Technical implementation, design, tooling |

---

## Repo Structure

```
AskStellaSpecs/
├── frontend/        # UI components, pages, design system
├── backend/         # API routes, serverless functions, data models
├── integrations/    # HeyGen, email, YouTube API, analytics
├── ux/              # User flows, wireframes, copy
├── infrastructure/  # Hosting, DNS, environment config
└── docs/            # Architecture overview, onboarding, decisions
```

---

## Tech Stack

| Layer | Technology | Rationale |
|-------|-----------|-----------|
| Front-end | Next.js | Fast, SEO-friendly, easy iteration |
| Backend | Serverless functions (Vercel/Netlify) | Scalable, low overhead |
| Database | Supabase (MVP) | Lightweight, real-time, easy to migrate |
| Video | HeyGen API | Stella avatar video generation |
| Email | Hover SMTP / StellaB@sestito.com | Already configured |
| CDN | Vercel Edge / Cloudflare | Fast global delivery |
| Analytics | Custom + Vercel Analytics | Track submissions, shares, returns |

---

## Key Infrastructure

| Asset | Detail |
|-------|--------|
| Domain | askstella.online |
| Public email | just@askstella.online |
| Stella DM | StellaB@sestito.com |
| Recon repo | https://github.com/LungNestoStellaB/AskStellaRecon |
| HeyGen | API ready (Captain has credentials) |

---

## Build Phases

- **Phase 1:** Foundation (front page + submission flow)
- **Phase 2:** Integration (HeyGen + email delivery)
- **Phase 3:** Polish (sharing + mobile + QA)

See `/docs/build-phases.md` for full detail.

---

*Last updated: 2026-05-02*
