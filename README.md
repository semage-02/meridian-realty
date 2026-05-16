# meridian-realty

# Meridian Realty — AI Lead Triage Demo

A portfolio project demonstrating an AI-powered lead qualification system for a fictional real estate brokerage. Built to showcase the pattern of automating inside sales / SDR work using no-code orchestration and large language models.

[**Live site →**](#) <!-- Add your Vercel URL here once deployed -->

---

## The problem

Mid-market brokerages typically convert under 2% of inbound leads into booked showings, largely due to slow response times (4+ hours median) and inconsistent qualification. Every minute of delay reduces conversion exponentially.

## The solution

An AI agent that responds to every inbound lead within 90 seconds, runs a qualifying conversation over SMS or WhatsApp, scores buyer intent, and either books a showing automatically or alerts a human agent for hot leads.

## Architecture

```
Website form (this site)
      │
      ▼
Make webhook (lead ingestion)
      │
      ▼
Airtable (lead database + conversation state)
      │
      ▼
Twilio (SMS / WhatsApp messaging)
      │
      ▼
OpenAI GPT-4o (qualification dialogue + scoring)
      │
      ▼
  ┌───┴───┐
  │       │
Cal.com   Slack
(booking) (hot lead alerts)
```

## Stack

- **Frontend:** Vanilla HTML / CSS / JS (no build step, deploys anywhere)
- **Hosting:** Vercel
- **Orchestration:** Make (formerly Integromat)
- **AI:** OpenAI GPT-4o
- **Messaging:** Twilio (SMS + WhatsApp)
- **Database:** Airtable
- **Calendar:** Cal.com
- **Notifications:** Slack

## Setup

1. Clone this repo
2. Open `index.html` and find the `MAKE_WEBHOOK_URL` constant
3. Replace it with your actual Make webhook URL
4. Deploy to Vercel (or any static host)

## Project status

This is an active portfolio build. See the `/docs` folder for the full case study and architecture decisions.

---

Built by Rajani · [The AI Internship](https://theaiinternship.com)
