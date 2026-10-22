# LinkedIn Auto-Poster: Trending Topics + Brain Dump

Creates and publishes LinkedIn posts with AI-generated images, with a human approval step over WhatsApp so nothing goes live without your OK.

## Two ways to start

**1. Trending topics (scheduled)**
- Runs at 9:00, 12:00 and 17:00 on weekdays.
- **Gemini 2.5 Flash** suggests 3 trending topics from the last 7 days (AI agents, mobile dev, backend, design, engineering careers).
- The topics are sent to you on WhatsApp; you tap a link to choose one.
- **Qwen 2.5 72B** (Hugging Face) writes a 150–200 word post on that topic.

**2. Brain dump (on demand)**
- Send your raw thoughts to the WhatsApp number.
- Gemini scores the idea and suggests improvements; you choose **Proceed** or **Rethink**.
- On Proceed, Qwen rewrites your thoughts into a post, with a strict prompt that forbids inventing facts or achievements.

## Approval and publishing

- The draft is sent to WhatsApp with **Approve** and **Reject & Regenerate** links.
- Rejections trigger a new draft with a different angle, up to **3 attempts**, then the final draft is sent to you to post manually.
- On approval, Gemini writes an image prompt, **Stable Diffusion XL** generates the image (with **Pollinations** as an automatic fallback if SDXL fails), and the post is published to LinkedIn with the image.
- You get a WhatsApp confirmation when it is live.

## Setup

- Credentials: WhatsApp Cloud API, Google Gemini, LinkedIn OAuth2.
- Replace `YOUR_HUGGINGFACE_TOKEN` (ideally move it into an n8n Header Auth credential).
- Replace `YOUR_PHONE_NUMBER`, `YOUR_WHATSAPP_PHONE_NUMBER_ID` and `YOUR_LINKEDIN_PERSON_ID`.
- Point your Meta app's webhook at the `whatsapp-brain-dump` webhook URL for the brain-dump path.
