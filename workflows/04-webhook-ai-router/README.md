# 04 — Smart Webhook AI Router

> Any incoming webhook → Claude analyzes the intent → routes to the right action automatically.

## What It Does

```
POST /ai-router { any JSON payload }
  → Claude classifies: route + priority + summary
  → Switch node routes to correct branch
  → Each branch handles its action (Slack, email, database, etc.)
```

## Use Cases

- **Customer support triage** — route tickets to right team automatically
- **Multi-service dispatcher** — one webhook endpoint for all events
- **AI-powered inbox** — classify emails/messages and take action
- **IoT event routing** — intelligent handling of sensor/device events

## Prerequisites

| Requirement | Where to get |
|-------------|-------------|
| `ANTHROPIC_API_KEY` | [console.anthropic.com](https://console.anthropic.com) |

## Setup

1. Set `ANTHROPIC_API_KEY` in n8n environment
2. Import `workflow.json`
3. **Customize the routes** — edit the `system` prompt in the Claude Classifier node to match your use case
4. Add action nodes after each Switch output branch
5. Activate and use the webhook URL as your universal endpoint

## Customizing Routes

Edit the system prompt in the `Claude Classifier` node:

```
Available routes: billing, feature-request, bug-report, general
```

Claude will automatically classify any incoming payload into one of these routes.

## Example Payload

```bash
curl -X POST https://your-n8n.com/webhook/ai-router \
  -H "Content-Type: application/json" \
  -d '{
    "message": "I cannot login to my account, it says password is wrong",
    "userId": "user-123",
    "timestamp": "2026-06-06T08:00:00Z"
  }'
```

## Example Response

```json
{
  "received": true,
  "route": "support",
  "priority": "high",
  "summary": "User locked out of account due to authentication issue"
}
```

## Extending This Template

- Add **Slack** nodes to notify different channels per route
- Add **Jira/Linear** nodes to create tickets automatically
- Add a **database** node to log all classified requests
- Chain with Template 03 to auto-generate responses
