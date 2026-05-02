# UX Flow — Guest Experience

**Last Updated:** 2026-05-02  
**Owner:** Stella (decisions), Engineering Lane (implementation)

---

## Design Principles

1. **Frictionless** — question submitted in <30 seconds
2. **Personal** — feels 1:1, not a chatbot
3. **Shareable** — every response is a potential viral moment
4. **Scalable** — handles 10 or 1,000 questions/day
5. **Mobile-first** — most traffic will be phones

---

## Page 1: Landing Page (askstella.online)

### Hero Section
- **Headline:** "Ask Stella Anything"
- **Subhead:** Brief, warm intro — who Stella is, what you get
- **CTA:** Large, prominent question input box
- **Tone:** Inviting, personal, not corporate

### Social Proof Section
- Recent #AskStella videos (YouTube API feed)
- "See what others are asking" — normalizes the action
- 3-6 featured questions/answers

### Question Form
- Name (optional, placeholder: "What should I call you?")
- Email (required, placeholder: "Where should I send your answer?")
- Question (text area, placeholder: "What's on your mind?")
- Submit button: "Ask Stella"

### Footer
- Simple: About | Contact (just@askstella.online) | #AskStella

---

## Page 2: Confirmation Page

Shown immediately after submission.

- **Headline:** "Stella's on it."
- **Body:** "Check your inbox — your answer is on its way."
- **Tone:** Warm, personal, no corporate fluff
- Optional: Share prompt ("Tell a friend to ask Stella too")

---

## Email 1: Confirmation (sent immediately)

**Subject:** "Stella got your question ⭐"

**Body:**
> Hi [Name / "there"],
>
> Stella received your question and is working on your answer.
>
> You'll hear back soon.
>
> — Stella ⭐

---

## Page 3: Answer Page (askstella.online/answer/{id})

- Embedded video player (Stella avatar answering)
- Question displayed above video
- Transcript below video (accessibility + SEO)
- Share buttons: Twitter, Facebook, WhatsApp
- CTA: "Ask another question"

---

## Email 2: Response Delivery

**Subject:** "Stella answered your question ⭐"

**Body:**
> Hi [Name / "there"],
>
> Your answer is ready.
>
> [Watch Stella's answer →] (button)
>
> Or share it: [shareable link]
>
> — Stella ⭐

---

## Mobile Considerations

- Single-column layout throughout
- Large tap targets (min 44px)
- Video player responsive (16:9, full width on mobile)
- Form inputs large enough to avoid zoom on iOS
- Share buttons native-sized

---

## Copy Tone

- Warm, direct, personal
- No jargon, no corporate speak
- Stella speaks in first person
- Short sentences, white space
- Feels like a message from a friend, not a service
