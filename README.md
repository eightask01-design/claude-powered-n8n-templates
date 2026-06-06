# Claude-Powered n8n Templates

Production-ready n8n workflow templates integrating Anthropic Claude AI.  
Import any template and deploy in under 60 seconds — no coding required.

[![n8n](https://img.shields.io/badge/n8n-v1.0%2B-orange)](https://n8n.io)
[![Claude](https://img.shields.io/badge/Anthropic-Claude-blueviolet)](https://anthropic.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## What This Repository Solves

If you are looking to:
- **Build a LINE chatbot that replies with Claude AI** → [Template 01](#01--claude-ai-line-chatbot)
- **Receive a personalized AI-generated morning briefing every day** → [Template 02](#02--ai-morning-brief)
- **Automatically generate blog posts, newsletters, or social content** → [Template 03](#03--ai-content-generator)
- **Route webhook requests to different handlers using AI classification** → [Template 04](#04--smart-webhook-ai-router)

---

## Templates

### 01 — Claude AI LINE Chatbot

**Problem**: You want an AI assistant that responds to LINE messages using Claude.  
**Solution**: n8n receives a LINE webhook → Claude generates a contextual reply → reply is sent back via LINE.

| Field | Value |
|---|---|
| Stack | n8n + Anthropic Claude (claude-opus-4-5) + LINE Messaging API |
| Trigger | Incoming LINE message |
| Output | Claude AI reply sent to LINE user |
| Required env vars | `ANTHROPIC_API_KEY`, `LINE_CHANNEL_ACCESS_TOKEN` |

[View template →](workflows/01-claude-line-chatbot/)

---

### 02 — AI Morning Brief

**Problem**: You want a personalized daily briefing delivered automatically each morning.  
**Solution**: Scheduled n8n trigger → Claude compiles a summary → delivers via LINE or email.

| Field | Value |
|---|---|
| Stack | n8n + Anthropic Claude (claude-haiku-4-5) + LINE / SMTP |
| Trigger | Daily schedule (8:00 AM) |
| Output | Personalized morning briefing sent to LINE or email |
| Required env vars | `ANTHROPIC_API_KEY`, `LINE_CHANNEL_ACCESS_TOKEN`, `LINE_USER_ID` |

[View template →](workflows/02-ai-morning-brief/)

---

### 03 — AI Content Generator

**Problem**: You want to automatically generate blog posts, newsletters, or social media content on demand.  
**Solution**: HTTP POST with a topic → Claude generates a full draft → returns via API and notifies via Slack.

| Field | Value |
|---|---|
| Stack | n8n + Anthropic Claude (claude-sonnet-4-6) + Slack Webhook |
| Trigger | HTTP POST request `{ "topic": "...", "type": "blog\|newsletter\|social" }` |
| Output | Full content draft returned in response body + Slack notification |
| Required env vars | `ANTHROPIC_API_KEY`, `SLACK_WEBHOOK_PATH` |

[View template →](workflows/03-ai-content-generator/)

---

### 04 — Smart Webhook AI Router

**Problem**: You want to intelligently classify and route incoming requests without hard-coded rules.  
**Solution**: Any webhook payload → Claude classifies intent and priority → routes to the correct handler.

| Field | Value |
|---|---|
| Stack | n8n + Anthropic Claude (claude-haiku-4-5) |
| Trigger | HTTP POST request (any payload) |
| Output | Classified route (`support` / `technical` / `sales` / `general`) + priority level |
| Required env vars | `ANTHROPIC_API_KEY` |

[View template →](workflows/04-webhook-ai-router/)

---

## Setup

### Step 1 — Get an Anthropic API key

Sign up at [console.anthropic.com](https://console.anthropic.com). New accounts include free credits.

### Step 2 — Set environment variables

All templates use n8n environment variables. **Never paste credentials directly into workflow JSON.**

```bash
# Add to your n8n .env file or host environment
ANTHROPIC_API_KEY=sk-ant-...

# Template 01 and 02
LINE_CHANNEL_ACCESS_TOKEN=...
LINE_USER_ID=...

# Template 03
SLACK_WEBHOOK_PATH=services/T.../B.../...
```

### Step 3 — Import and activate

1. Download `workflow.json` from the template folder
2. In n8n: **Workflows → Import from file**
3. Activate the workflow

---

## Who These Templates Are For

| Role | Recommended template |
|---|---|
| Developer building an AI chatbot prototype | 01 LINE Chatbot |
| Individual wanting automated daily AI briefings | 02 Morning Brief |
| Content creator or marketer automating drafts | 03 Content Generator |
| Developer needing intelligent webhook dispatch | 04 AI Router |

---

## Frequently Asked Questions

**Q: Can I use these with n8n Cloud?**  
A: Yes. Both self-hosted and n8n Cloud (v1.0+) are supported.

**Q: Do I need a paid Anthropic plan?**  
A: No. Free-tier API credits work for all templates. Costs scale with usage.

**Q: Can I swap Claude for a different model?**  
A: Yes. Change the `"model"` field in the HTTP Request node to any supported Claude model ID.

**Q: Are credentials safe?**  
A: All credentials are referenced via `$env.*` — nothing is hardcoded in the JSON files.

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](.github/CONTRIBUTING.md) for guidelines.

## License

MIT — free for personal and commercial use.

---

*Built with [Claude](https://anthropic.com) + [n8n](https://n8n.io)*
