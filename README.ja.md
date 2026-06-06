# 🤖 Claude × n8n テンプレート集

> **Anthropic Claude AIを使ったn8nワークフロー。インポートして60秒で動かせる。**

---

## ⚠️ 使い始める前に

全テンプレートは **Anthropic APIキー** が必要です。JSONに直接貼り付けないでください。

n8nの環境変数として設定してください：
```bash
# .envファイルまたは環境変数に設定
ANTHROPIC_API_KEY=sk-ant-...
```

---

## 📦 テンプレート一覧

| # | テンプレート名 | 用途 | 推奨モデル |
|---|-------------|------|-----------|
| [01](workflows/01-claude-line-chatbot/) | **Claude AI LINE チャットボット** | LINEメッセージにClaudeが返信 | claude-opus-4-5 |
| [02](workflows/02-ai-morning-brief/) | **AI 朝ブリーフィング** | 毎朝のタスクサマリーをLINE/メール送信 | claude-haiku-4-5 |
| [03](workflows/03-ai-content-generator/) | **AIコンテンツ生成器** | ブログ記事・メルマガの自動生成 | claude-sonnet-4-6 |
| [04](workflows/04-webhook-ai-router/) | **Webhook AIルーター** | Claudeによるインテリジェントルーティング | claude-haiku-4-5 |

---

## 🚀 使い方

1. テンプレートフォルダから `workflow.json` をダウンロード
2. n8nで **Workflows → Import from file**
3. `ANTHROPIC_API_KEY` を環境変数に設定
4. 必要なサービス認証情報を設定（LINE, SMTP等）
5. **Activate** して完了

---

## 📄 ライセンス

MIT — 個人・商用利用無料

---

*[Claude](https://anthropic.com) + [n8n](https://n8n.io) で作成*
