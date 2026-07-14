# Alex — AI Voice Agent for Riverstone Place

> 🎥 [Loom walkthrough](https://www.loom.com/share/10a8ea3f81c54ef0af553a1b144cd91e?sid=0c18def1-2c4b-4d47-b8ea-409a3d402231)

---

## Problem

Riverstone Place, a real estate developer, was missing inbound sales calls after hours and during peak periods. Every missed call was a lost lead — and hiring 24/7 staff wasn't viable.

## Build

Alex is an AI voice agent that answers every call, qualifies buyers, and books appointments — no human needed until the meeting.

- **Telephony**: Twilio SIP trunking routes calls to the agent
- **Voice Runtime**: Retell.ai handles speech-to-text, text-to-speech, and real-time inference
- **LLM**: OpenAI GPT-5 mini — low latency, cost-effective for voice
- **Automation**: N8N workflows log structured JSON call summaries into Google Sheets
- **Logs**: Retell.ai stores full transcripts + call recordings

## Result

Alex handles the full qualification flow: greets callers, asks structured questions (budget, bedrooms, parking, location, timeframe, finance), confirms answers, offers a 15-minute booking, and outputs structured data. The sales team walks into every call pre-briefed.

---

## Stack

`twilio` · `retell-ai` · `openai` · `n8n` · `google-sheets`

## Prompt Design

Built with core human-machine interaction principles (RACI). The system prompt keeps Alex polite, professional, and on-script:

> *You are a polite real estate sales assistant. Greet callers, ask qualifying questions, confirm their answers, offer a 15-min booking, then output a JSON object. Always stay concise and professional.*

**Flow:** Greeting → Structured Q&A → Confirmation → Booking offer → JSON output → Google Sheets log.