# 🤖 Claude-Powered n8n Templates

> **Production-ready n8n workflows with Anthropic Claude AI — import and run in 60 seconds.**

[![n8n](https://img.shields.io/badge/n8n-compatible-orange)](https://n8n.io)
[![Claude](https://img.shields.io/badge/Anthropic-Claude-blueviolet)](https://anthropic.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## ⚠️ Before You Start

These workflows require an **Anthropic API key**. Never paste your key directly into the workflow JSON.

Set it as an n8n environment variable:
```bash
# In your n8n .env file or environment
ANTHROPIC_API_KEY=sk-ant-...
```

---

## 📦 Templates

| # | Template | Use Case | Claude Model |
|---|----------|----------|-------------|
| [01](workflows/01-claude-line-chatbot/) | **Claude AI LINE Chatbot** | Reply to LINE messages with Claude AI | claude-opus-4-5 |
| [02](workflows/02-ai-morning-brief/) | **AI Morning Brief** | Daily productivity summary via LINE/email | claude-haiku-4-5 |
| [03](workflows/03-ai-content-generator/) | **AI Content Generator** | Auto-generate blog posts / newsletters | claude-sonnet-4-6 |
| [04](workflows/04-webhook-ai-router/) | **Smart Webhook AI Router** | Claude-powered request routing | claude-haiku-4-5 |

---

## 🚀 Quick Start

1. **Download** the `workflow.json` from any template folder
2. In n8n: **Workflows → Import from file**
3. Set your `ANTHROPIC_API_KEY` environment variable
4. Configure any service credentials (LINE, SMTP, etc.)
5. **Activate** and you're live

---

## 📋 Requirements

- n8n v1.0+ (self-hosted or cloud)
- Anthropic API key ([get one here](https://console.anthropic.com))
- Service-specific credentials (LINE, SMTP, etc.) — see each template's README

---

## 🗂 Template Details

### 01 — Claude AI LINE Chatbot
Send a message to your LINE bot → Claude replies intelligently.
Perfect for: personal AI assistant, team Q&A bot, customer support prototype.

### 02 — AI Morning Brief
Every morning at 8am, Claude compiles your tasks and sends a personalized briefing.
Perfect for: productivity automation, daily standup prep.

### 03 — AI Content Generator
Trigger with a topic → Claude generates a full blog post/newsletter draft and sends it to your inbox.
Perfect for: content marketers, newsletter creators, bloggers.

### 04 — Smart Webhook AI Router
Any incoming webhook → Claude analyzes intent → routes to the right action.
Perfect for: multi-step automations, intelligent dispatch systems.

---

## 🤝 Contributing

PRs welcome! See [CONTRIBUTING.md](.github/CONTRIBUTING.md) for guidelines.

If you build something cool with these templates, share it in [n8n Community](https://community.n8n.io) and tag `@n8n-claude-templates`.

---

## 📄 License

MIT — free for personal and commercial use.

---

*Built with ❤️ using [Claude](https://anthropic.com) + [n8n](https://n8n.io)*
