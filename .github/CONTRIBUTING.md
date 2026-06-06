# Contributing

## Adding a New Template

1. Create a folder: `workflows/XX-your-template-name/`
2. Add `workflow.json` — exported from n8n
3. Add `README.md` with: What It Does / Prerequisites / Setup / Extending
4. **Never hardcode API keys** — use `$env.YOUR_KEY_NAME`
5. Test that the workflow imports cleanly into a fresh n8n instance
6. Open a PR with the template folder

## Template Quality Checklist

- [ ] All credentials use `$env.` variables
- [ ] README has Prerequisites table
- [ ] Workflow name follows `[n8n Template] Your Name` format
- [ ] `active: false` in the JSON (don't ship activated workflows)
- [ ] Works with n8n v1.0+
