# WhatsApp Multimodal AI Agent

A 24/7 AI assistant on WhatsApp that handles every common message type and replies in the same format the user prefers.

## Flow

1. **WhatsApp Trigger** receives an incoming message.
2. **Input type** routes it by type:
   - **Text**: passed straight to the agent.
   - **Voice note**: downloaded and transcribed with **Groq Whisper (large-v3)**.
   - **Image**: downloaded and described with **Gemini 2.5 Flash-Lite** vision.
   - **PDF**: downloaded and its text extracted.
3. **AI Agent** (Gemini 2.5 Flash-Lite) answers, with a **10-message memory window per user** keyed on their WhatsApp ID.
4. If the user sent a voice note, the reply is converted to speech with **ElevenLabs** and sent back as audio; otherwise it is sent as text.

## Setup

- WhatsApp Cloud API credential (Meta for Developers). A step-by-step sticky note inside the workflow explains how to get one.
- Google Gemini credential.
- Groq API key (header auth) for transcription.
- ElevenLabs API key and voice ID in the text-to-speech node.
- Replace `YOUR_WHATSAPP_PHONE_NUMBER_ID` in the send nodes.

## Optional (not wired yet)

The workflow includes nodes that are not connected to the main flow yet:
- "Sorry, only PDF files" and "not supported" replies for other file and message types.
- Logging conversations to Google Sheets and syncing contacts to Chatwoot.

Fill in the placeholders and connect them if you need them.
