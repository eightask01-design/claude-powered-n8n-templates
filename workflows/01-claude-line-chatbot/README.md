# 01 — Claude AI LINE Chatbot

> Send a LINE message → Claude AI replies instantly.

## What It Does

```
User sends LINE message
  → n8n receives webhook
  → Extracts text
  → Sends to Claude API
  → Replies back via LINE
```

## Prerequisites

| Requirement | Where to get |
|-------------|-------------|
| n8n v1.0+ | [n8n.io](https://n8n.io) |
| `ANTHROPIC_API_KEY` | [console.anthropic.com](https://console.anthropic.com) |
| `LINE_CHANNEL_ACCESS_TOKEN` | [LINE Developers Console](https://developers.line.biz) |
| LINE Messaging API channel | LINE Developers Console |

## Setup (5 steps)

1. **Set environment variables** in n8n:
   ```
   ANTHROPIC_API_KEY=sk-ant-...
   LINE_CHANNEL_ACCESS_TOKEN=your-line-token
   ```

2. **Import** `workflow.json` into n8n

3. **Activate** the workflow — copy the webhook URL shown

4. In LINE Developers Console → **Messaging API** → Webhook URL → paste the n8n URL

5. Send yourself a LINE message to test

## Customization

- Change `"model"` to `claude-haiku-4-5` for faster/cheaper responses
- Edit the `"system"` prompt to give Claude a persona
- Add message history by storing conversations in a database node

## Cost Estimate

~$0.001–0.005 per message with claude-opus-4-5.
Switch to `claude-haiku-4-5` for ~10x cheaper responses.
