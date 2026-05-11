# MEET & GREET — Engineering Specs Addendum
**Date:** 2026-05-11
**From:** Stella
**To:** Engineering Lane
**Status:** ADDENDUM to ENGINEERING-BRIEF.md — Phase 1 extension

---

## What This Is

An extension to the existing AskStella Phase 1 brief. The core site architecture is unchanged. This adds one new feature: the **Agents Lounge / Meet & Greet**.

**Existing brief still stands.** This document only describes what's new.

---

## The Feature

A "Meet & Greet" button on the AskStella landing page (and/or category pages) that opens a modal — the **Agents Lounge**.

Inside the lounge, users can browse a curated set of AI agents and launch a short intro session with any of them, directly inside the AskStella site.

**The promise to the user:**
> "Try before you commit. Meet the agent. See if it's right for you."

**The promise to the agent founders:**
> "We send you warm, informed leads. They already know what you do."

---

## User Flow

1. User lands on AskStella
2. Sees "Meet & Greet" button (or "Agents Lounge" — TBD on copy)
3. Clicks → modal opens
4. Lounge card grid appears: 4 agents (Phase 1)
5. User clicks "Enter the room" on any card
6. Embed loads inside the modal (iframe or SDK component)
7. Privacy banner always visible: "You're talking directly with [Agent]. AskStella doesn't see your conversation."
8. Exit button always accessible — returns to lounge card grid
9. User can try multiple agents in one session

---

## Phase 1 Agent Seats (4 confirmed)

| Agent | Integration Method | SDK/Docs |
|---|---|---|
| **MyClaw (OpenClaw)** | Direct embed / iframe | We control this |
| **ChatGPT (OpenAI)** | ChatKit React SDK | https://developers.openai.com/api/docs/guides/chatkit |
| **Gemini (Google)** | Google AI API / iframe | https://ai.google.dev/api |
| **Canva AI** | iframe embed | https://www.canva.com/developers/ |

---

## Technical Spec

### New Components Required

**1. MeetAndGreet button**
- Placement: Hero section of landing page + optional on category pages
- Style: Secondary CTA (primary CTA remains "Find my agent")
- Label: "Meet & Greet" or "Agents Lounge" (copy TBD)

**2. Lounge Modal**
- Full-screen overlay or large centered modal
- Responsive (mobile-first)
- Contains: lounge card grid + embed container (toggled)
- Close button always visible

**3. Lounge Card Grid**
- 4 cards (Phase 1), expandable to 8 (Phase 2)
- Each card: agent avatar + name + one-line pitch + "Enter the room" button
- Card style: warm, lounge-like — not clinical

**4. Embed Container**
- Renders inside the modal when user selects an agent
- Hosts: iframe OR React SDK component depending on agent
- Privacy banner: fixed position, always visible
- Exit button: returns to card grid (does not close modal)
- Session is client-side only — no server logging of conversation content

**5. Privacy Banner (mandatory)**
```
You're now talking directly with [Agent Name].
AskStella doesn't see your conversation. [Exit ↩]
```
- Non-dismissable
- Visible at all times during embed session

---

## Affiliate Link Tracking

All outbound links from the lounge (sign-up, upgrade, learn more) must include UTM parameters:

```
utm_source=askstella
utm_medium=lounge
utm_campaign=meet-and-greet
utm_content=[agent-name]
```

This is how we track which agents drive conversions. Required from day one.

---

## Data Architecture

**What AskStella stores:**
- Session initiated (timestamp, agent selected) — for analytics only
- Referral click (UTM tracking) — for affiliate reporting

**What AskStella does NOT store:**
- Conversation content
- User inputs
- Any personal data entered during the embed session

All conversation data stays with the agent's own backend. We are the room, not the recorder.

---

## What Does NOT Change

- Landing page structure: unchanged
- Category pages: unchanged
- Agent detail pages: unchanged
- Tech stack: Next.js + serverless — no change
- Backend: no new backend required for Phase 1
- Database: not required for Phase 1 (lightweight analytics only)

---

## Engineering Impact Assessment

| Item | Effort estimate |
|---|---|
| MeetAndGreet button | Minimal — 1 component |
| Lounge Modal | Medium — modal + state management |
| Lounge Card Grid | Low — static data, 4 cards |
| ChatKit integration (OpenAI) | Medium — React SDK, session token endpoint needed |
| Gemini embed | Low-Medium — iframe or API |
| Canva embed | Low — iframe |
| MyClaw embed | Low — we control this |
| Privacy banner | Minimal |
| UTM tracking | Minimal — append to existing links |
| **Total Phase 1** | **~3-5 days engineering** |

---

## Phase 2 Preview (not for now)

- Add Perplexity (API mode embed)
- Add Claude (via embeddable.co wrapper)
- Expand card grid to 6-8 agents
- Add "Apply for a seat" flow (agent founders)

---

## Questions for Engineering

1. ChatKit requires a backend session token endpoint — can we add a lightweight serverless function for this? (FastAPI or Next.js API route)
2. Canva embed — confirm iframe permissions and CSP headers
3. MyClaw embed — what's the cleanest way to embed an OpenClaw session in an iframe? (Stella to confirm with Captain)

---

## Chain of Command

- **Captain:** WHY — approved the concept
- **Stella:** WHAT — this spec
- **Engineering:** HOW — implementation

No surprises. Build what's here. Questions route through Stella.

— Stella ⭐
