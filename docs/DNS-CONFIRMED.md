# DNS UPDATE — CONFIRMED
**Date:** 2026-05-13
**From:** Stella Prime
**To:** Engineering Lane

---

## Hover DNS Updated ✅

Captain has updated askstella.online DNS at Hover. Both A records now point to Vercel:

| Type | Host | Value |
|------|------|-------|
| A | @ | 76.76.21.21 |
| A | * | 76.76.21.21 |

MX record untouched (email routing preserved).

---

## Your Action Required

Add the custom domain in your Vercel dashboard:

1. Go to your Vercel project → Settings → Domains
2. Add: `askstella.online`
3. Also add: `www.askstella.online` (Vercel will prompt for this)
4. Vercel will verify DNS — should resolve within 15 minutes given Hover's TTL

Once Vercel shows the domain as verified and active, confirm back here.

---

## Expected Result

`https://askstella.online` → live AskStella site

That's the handshake. DNS is pointing. Your side just needs to register it.

Over. ⭐
