# PHASE 2 ORDERS — AskStella
**Date:** 2026-05-12
**From:** Stella Prime
**To:** Engineering Lane (Falco)

---

Outstanding work. Foundation is confirmed live and clean.

https://frontend-gilt-seven-20.vercel.app

Hero copy landed perfectly. Categories rendering. Form live. This is exactly what was specced. Well done. 🦅

---

## Phase 2 Mission

Two workstreams. Read both before starting either.

### Workstream A — Custom Domain

Point askstella.online to the Vercel deployment.

In Vercel dashboard:
- Add custom domain: `askstella.online`
- Vercel will give you DNS records to add
- Relay those DNS records to Stella Prime — Captain manages DNS at Hover

Do not touch Hover DNS yourself. Relay the records and we handle it from here.

### Workstream B — Meet & Greet / Agents Lounge

You already built the components (AgentsLoungeModal, AgentCard, EmbedContainer, PrivacyBanner). Good instinct reading ahead.

Full spec: `docs/MEET-AND-GREET-SPECS.md`

**Phase 1 lounge seats (4 agents):**

| Agent | Integration | Notes |
|---|---|---|
| MyClaw | iframe / TBD | Stella Prime to confirm embed path |
| ChatGPT | ChatKit React SDK | `@openai/chatkit-react` — needs OpenAI API key |
| Gemini | Google AI iframe | Google AI Studio |
| Canva AI | iframe | Check CSP headers |

**Three questions to answer before wiring:**
1. ChatKit — confirm session token endpoint is working (`/api/lounge-token/route.ts` already exists — test it)
2. Canva iframe — confirm CSP headers allow embed
3. MyClaw embed path — standing by for Stella Prime confirmation

File your questions in `docs/MEET-AND-GREET-QUESTIONS.md` and we will turn them around fast.

---

## Priority Order

1. Custom domain first (quick win, makes everything real)
2. Meet & Greet wiring second

Standing by. Over. ⭐
