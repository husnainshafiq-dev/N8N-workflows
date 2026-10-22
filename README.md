# n8n AI Automations

Production-style AI automation workflows built with [n8n](https://n8n.io), combining LLMs, speech, vision and image generation with WhatsApp, LinkedIn, Google Sheets and Apify.

| Workflow | What it does | Key tech |
|---|---|---|
| [WhatsApp AI Agent](./whatsapp-ai-agent) | Multimodal assistant on WhatsApp: understands text, voice notes, images and PDFs, remembers context per user, and replies by text or voice | Meta WhatsApp Cloud API, Gemini 2.5 Flash-Lite, Groq Whisper, ElevenLabs |
| [LinkedIn Auto-Poster](./linkedin-auto-poster) | Researches trending topics or turns your own ideas into LinkedIn posts with AI images, with human approval over WhatsApp before anything is published | Gemini 2.5 Flash, Qwen 2.5 72B (Hugging Face), Stable Diffusion XL, LinkedIn API |
| [Google Maps Lead Scraper](./google-maps-lead-scraper) | Scrapes businesses from Google Maps, cleans and deduplicates them, and exports leads to Google Sheets and CSV | Apify, JavaScript, Google Sheets |

## How to use

1. In n8n, go to **Workflows → Import from File** and pick the `.json` file from a folder.
2. Open each node marked with a placeholder (`YOUR_...`) and fill in your own values.
3. Create the credentials n8n asks for (WhatsApp, Gemini, LinkedIn, Google Sheets) under **Credentials**. Store API keys there rather than in node headers.
4. Activate the workflow.

## Security note

All API keys, phone numbers, account IDs and credential references have been replaced with placeholders. Never commit real tokens; use n8n credentials or environment variables instead.

## Author

**Husnain Shafiq**: [LinkedIn](https://linkedin.com/in/husnain-shafiq1) · [GitHub](https://github.com/husnainshafiq-dev) · [Portfolio](https://husnain-shafiq.vercel.app)
