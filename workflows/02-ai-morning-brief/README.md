# 02 — AI Morning Brief

> Every morning at 8am, Claude generates a personalized productivity briefing and sends it via LINE.

## What It Does

```
8:00 AM trigger
  → Build context (date + today's tasks)
  → Claude generates motivating morning brief
  → Push notification via LINE
```

## Prerequisites

| Requirement | Where to get |
|-------------|-------------|
| `ANTHROPIC_API_KEY` | [console.anthropic.com](https://console.anthropic.com) |
| `LINE_CHANNEL_ACCESS_TOKEN` | [LINE Developers Console](https://developers.line.biz) |
| `LINE_USER_ID` | Your LINE user ID (use `Profile` API to get it) |

## Setup

1. Set environment variables in n8n
2. Import `workflow.json`
3. Edit the `Build Context` node — replace the sample tasks array with your actual tasks source (Google Sheets, Notion, etc.)
4. Activate

## Extending This Template

**Connect to real task sources:**
- Add a **Google Sheets** node before `Build Context` to pull today's tasks
- Add a **Notion** node to fetch tasks from your Notion database
- Add a **Google Calendar** node to include today's events

**Send to other channels:**
- Replace `Send via LINE` with an **SMTP** node to get email delivery
- Or use a **Slack** node for team standup automation

## Example Output

> Good morning! It's Tuesday, June 6th — a great day to make progress.
> Your key focus today: team standup at 10am and reviewing those pull requests.
> Pro tip: tackle the PR reviews first thing while your mind is fresh. You've got this! 🚀
