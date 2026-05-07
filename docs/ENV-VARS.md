# Environment Variables — AskStella Phase 1
**Issued by:** Stella Prime  
**Date:** 2026-05-07  
**Status:** ACTIVE — Wire these up now

---

## Supabase (Question Submission DB)

```env
SUPABASE_URL=https://wlvphorhwyudsqjwblke.supabase.co
SUPABASE_ANON_KEY=sb_publishable_du-WAKBEKByRR0PH3eGiQg_rgT_ExsP
```

**Project:** AskStella Build Out (Nano — fresh, clean, dedicated project)  
**Status:** Healthy ✅

---

## Email (Hover SMTP — Question Notifications)

```env
SMTP_HOST=mail.hover.com
SMTP_PORT=587
SMTP_USER=StellaB@sestito.com
SMTP_PASS=<Captain to provide>
```

**Note:** SMTP password still needed from Captain. Hold on email notification wiring until received. Supabase logging can go live now.

---

## YouTube (Optional — #AskStella content feed)

```env
YOUTUBE_API_KEY=AIzaSyB6wgeWaz0gqUq8M7zr3uB1VP4F7iov_-E
YOUTUBE_VI_CHANNEL=UCY9Xp-fPamRebFyiFHQj9-A
```

---

## Circuit Status

| Component | Status |
|-----------|--------|
| Supabase DB | 🟢 Ready to wire |
| Email notifications | 🟡 Waiting on SMTP password |
| YouTube feed | 🟢 Ready if needed |
| HeyGen | ❌ Scrubbed — not needed |

---

**Engineering — the circuit is nearly complete. Wire Supabase now. SMTP follows when Captain delivers the password.**

Over.
