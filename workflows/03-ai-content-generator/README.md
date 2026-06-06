# 03 — AI Content Generator

> POST a topic → Claude generates a full blog post, newsletter issue, or 3 social media posts.

## What It Does

```
POST /generate-content { "topic": "...", "type": "blog|newsletter|social" }
  → Build tailored prompt based on content type
  → Claude generates full content
  → Returns JSON response + notifies Slack
```

## Prerequisites

| Requirement | Where to get |
|-------------|-------------|
| `ANTHROPIC_API_KEY` | [console.anthropic.com](https://console.anthropic.com) |
| `SLACK_WEBHOOK_PATH` | Optional — Slack Incoming Webhooks (for notifications) |

## Setup

1. Set `ANTHROPIC_API_KEY` in n8n environment
2. Import `workflow.json`
3. (Optional) Set `SLACK_WEBHOOK_PATH` or remove the Slack node
4. Activate and copy the webhook URL

## Usage

```bash
# Generate a blog post
curl -X POST https://your-n8n.com/webhook/generate-content \
  -H "Content-Type: application/json" \
  -d '{
    "topic": "How to automate your morning routine with AI",
    "type": "blog",
    "language": "English",
    "tone": "friendly and practical"
  }'

# Generate a newsletter
curl -X POST https://your-n8n.com/webhook/generate-content \
  -H "Content-Type: application/json" \
  -d '{"topic": "n8n automation tips", "type": "newsletter"}'

# Generate social posts
curl -X POST https://your-n8n.com/webhook/generate-content \
  -H "Content-Type: application/json" \
  -d '{"topic": "AI productivity hacks", "type": "social"}'
```

## Response Format

```json
{
  "status": "success",
  "topic": "How to automate...",
  "contentType": "blog",
  "content": "# How to Automate Your Morning Routine with AI\n\n..."
}
```

## Extending This Template

- Add a **Google Docs** node to save content automatically
- Add a **Beehiiv/Mailchimp** node to publish newsletters directly
- Add a **Buffer/Hootsuite** node to schedule social posts
- Chain multiple topics via a **Google Sheets** trigger for bulk generation
