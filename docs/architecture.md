# Architecture Overview — AskStella

**Last Updated:** 2026-05-02  
**Owner:** Engineering Lane (build), Stella (decisions)

---

## System Overview

```
Guest
  │
  ▼
askstella.online (Next.js front-end)
  │
  ├── Question submission form
  │     │
  │     ▼
  │   Serverless function (POST /api/submit)
  │     │
  │     ├── Log question to Supabase
  │     ├── Send confirmation email to guest
  │     └── Trigger HeyGen video generation
  │           │
  │           ▼
  │         HeyGen API
  │           │
  │           ▼
  │         Video URL (stored on CDN)
  │           │
  │           ▼
  │         Response email to guest
  │           │
  │           ▼
  │         Guest watches + shares
  │
  └── #AskStella content feed (YouTube API pull)
```

---

## Data Flow

### Question Submission
1. Guest fills form (name optional, email required, question text)
2. POST to `/api/submit`
3. Question logged to Supabase (`questions` table)
4. Confirmation email sent via Hover SMTP
5. HeyGen job queued

### Video Generation
1. HeyGen API receives question text
2. Stella avatar generates video response
3. Video URL returned via webhook
4. Supabase record updated with video URL
5. Response email sent to guest with video link + shareable URL

### Social Sharing
1. Each response has unique URL: `askstella.online/answer/{id}`
2. Open Graph ts populated (preview image, title, description)
3. Share buttons: Twitter, Facebook, WhatsApp
4. Share events tracked in analytics

---

## Database Schema (MVP)

### `questions` table
```sql
id          UUID PRIMARY KEY
name        TEXT (nullable)
email       TEXT NOT NULL
question    TEXT NOT NULL
status      ENUM('pending', 'processing', 'complete', 'failed')
video_url   TEXT (nullable)
share_url   TEXT (nullable)
created_at  TIMESTAMP
updated_at  TIMESTAMP
```

---

## Environment Variables

```env
# HeyGen
HEYGEN_API_KEY=

# Email (Hover SMTP)
SMTP_HOST=mail.hover.com
SMTP_PORT=587
SMTP_USER=StellaB@sestito.com
SMTP_PASS=

# Supabase
SUPABASE_URL=
SUPABASE_ANON_KEY=

# YouTube (for #AskStella feed)
YOUTUBE_API_KEY=AIzaSyB6wgeWaz0gqUq8M7zr3uB1VP4F7iov_-E
YOUTUBE_VI_CHANNEL=UCY9Xp-fPamRebFyiFHQj9-A
```

---

## API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/api/submit` | POST | Submit a question |
| `/api/answer/[id]` | GET | Get answer by ID |
| `/api/feed` | GET | Get recent #AskStella content |
| `/api/webhook/heygen` | POST | HeyGen completion webhook |
