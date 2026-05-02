# HeyGen Integration Spec

**Last Updated:** 2026-05-02  
**Owner:** Engineering Lane (implementation), Stella (decisions)

---

## Overview

HeyGen generates personalized video responses from Stella's avatar. Each guest question triggers a video generation job. The completed video is delivered via email and hosted on a shareable page.

---

## API Flow

```
Question submitted
      │
      ▼
POST /api/submit
      │
      ▼
HeyGen API: Create video job
  - Avatar: Stella
  - Script: Generated response to question
  - Language: English (v1)
      │
      ▼
HeyGen webhook: Job complete
  - Video URL returned
      │
      ▼
Supabase: Update question record with video_url
      │
      ▼
Email: Send response to guest with video link
```

---

## HeyGen API Endpoints

| Action | Endpoint | Method |
|--------|----------|--------|
| Create video | `/v2/video/generate` | POST |
| Check status | `/v1/video_status.get` | GET |
| List avatars | `/v2/avatars` | GET |

**Base URL:** `https://api.heygen.com`

---

## Video Generation Request

```json
{
  "video_inputs": [{
    "character": {
      "type": "avatar",
      "avatar_id": "<stella_avatar_id>",
      "avatar_style": "normal"
    },
    "voice": {
      "type": "text",
      "input_text": "<generated_response>",
      "voice_id": "<stella_voice_id>"
    }
  }],
  "dimension": {
    "width": 1280,
    "height": 720
  },
  "aspect_ratio": "16:9"
}
```

---

## Webhook Handler

Engineering Lane must implement `/api/webhook/heygen`:

1. Receive POST from HeyGen on job completion
2. Extract `video_url` from payload
3. Update Supabase `questions` record
4. Trigger response email to guest

---

## Response Generation

For v1, Stella (or a prompt template) generates the script for each question. Engineering Lane should implement a simple prompt pipeline:

1. Receive question text
2. Send to LLM with Stella persona prompt
3. Return script (max 60 seconds of speech ~150 words)
4. Pass script to HeyGen

---

## Fallback

If HeyGen fails or times out:
- Send text-only response email
- Log failure in Supabase
- Flag for manual review

---

## Rate Limits & Cost

- HeyGen is pay-as-you-go
- Batch where possible — avoid one-item loops
- Monitor credit usage weekly
- Alert if daily spend exceeds threshold (TBD by Captain)
