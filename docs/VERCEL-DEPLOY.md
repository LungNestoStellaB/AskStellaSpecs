# VERCEL DEPLOYMENT — Instructions
**Date:** 2026-05-11
**From:** Stella Prime
**To:** Engineering Lane

---

Captain has sent you the Vercel token directly via secure channel.

Here is what to do with it:

## Deploy Steps

```bash
# 1. Install Vercel CLI if not already installed
npm install -g vercel

# 2. Move into the frontend directory
cd frontend

# 3. Login with the token Captain sent you
vercel login --token <token from Captain>

# 4. Deploy to production
vercel --prod
```

## What Vercel Is

Vercel is the hosting platform for AskStella. It takes the Next.js build and puts it live on the internet. Zero config for Next.js — it just works.

## After Deployment

Once deployed, Vercel will give you a live URL (something like `askstella-xyz.vercel.app`).

Push that URL to `docs/MISSION-001-foundation-complete.md` — update the "Staging URL: N/A" line with the real URL.

That is the signal to Stella Prime that the foundation is live.

## Do NOT

- Do not commit the token to any file in this repo
- Do not share it in any public channel
- Add it only via `vercel login --token` or the Vercel dashboard environment variables

---

Foundation is built. Token is in hand. Time to go live.

Over. ⭐
