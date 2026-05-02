# Build Phases — AskStella

**Last Updated:** 2026-05-02  
**Owner:** Engineering Lane (execution), Stella (sign-off), Captain (final approval)

---

## Phase 1: Foundation (Week 1-2)

**Goal:** Working front page + question submission → email confirmation

### Deliverables
- [ ] Next.js project scaffolded and deployed to Vercel
- [ ] Landing page (hero, form, social proof section)
- [ ] Question submission form (name, email, question)
- [ ] POST `/api/submit` — logs to Supabase, sends confirmation email
- [ ] Confirmation page (post-submit)
- [ ] Basic mobile layout
- [ ] Domain pointed: askstella.online → Vercel

### Sign-off
- Stella reviews UX/copy
- Captain approves landing page design

---

## Phase 2: Integration (Week 2-3)

**Goal:** End-to-end flow — question → HeyGen video → response email

### Deliverables
- [ ] HeyGen API integrated (video generation triggered on submit)
- [ ] Webhook handler (`/api/webhook/heygen`) — updates DB on completion
- [ ] Answer page (`/answer/{id}`) — video player + transcript + share buttons
- [ ] Response email sending with video link
- [ ] YouTube API feed on landing page (#AskStella content)
- [ ] Analytics tracking (submissions, completions, shares)

### Sign-off
- Stella tests end-to-end flow
- Captain reviews answer page design

---

## Phase 3: Polish (Week 3-4)

**Goal:** Launch-ready — polished, tested, scalable

### Deliverables
- [ ] Social sharing (Open Graph tags, unique shareable URLs)
- [ ] Mobile optimization (all pages)
- [ ] Load testing (simulate traffic spike)
- [ ] Error handling (HeyGen fallback, email fallback)
- [ ] Analytics dashboard (Stella + Captain access)
- [ ] SEO basics (meta tags, sitemap)
- [ ] Final QA pass

### Sign-off
- Stella final UX review
- Captain launch approval

---

## Launch

**Target:** Early May 2026  
**Trigger:** Captain says "wheels up"  
**Announcement:** #AskStella across all channels

---

## Progress Tracking

Engineering Lane commits progress to this repo daily.  
Stella reviews and signs off on each phase.  
Captain approves before moving to next phase.
