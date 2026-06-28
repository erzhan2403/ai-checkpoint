# 🧭 AI Checkpoint

**Never lose your project context when switching AI chats again.**

When a conversation with Claude, ChatGPT, or Gemini gets long, it gets slow, expensive, and hits limits faster. The usual fix — "summarize this chat" — gives you a story of the conversation, not the *state* of your project.

**AI Checkpoint** is a set of battle-tested prompts that capture a structured *snapshot* of your project — architecture, decisions, what's done, what's broken, and the next step — so you can drop it into a fresh chat and keep building with zero context loss.

> Summaries retell the conversation. Checkpoints transfer the project.

---

## 🤔 Why this exists

If you build anything non-trivial with AI, you've felt this:

- The chat is 200 messages deep and every reply takes forever.
- You hit your usage limit mid-task.
- You start a new chat and spend 20 minutes re-explaining your stack, your decisions, and that one bug.
- The model "forgets" *why* you chose something three sessions ago and quietly undoes it.

A **summary** doesn't fix this. A **checkpoint** does — because it stores decisions *and the reasoning behind them*, the current architecture, and the exact next step.

---

## 🚀 Quick start (30 seconds)

1. At the **end** of a working session, paste [`prompts/checkpoint-dev.md`](prompts/checkpoint-dev.md) into your AI chat.
2. Copy the structured checkpoint it generates.
3. In a **new** chat, paste [`prompts/resume.md`](prompts/resume.md) followed by your checkpoint.
4. Keep building — the model is fully caught up.

That's it. No install, no extension, no account.

---

## 📦 What's inside

| Prompt | Use it when |
|---|---|
| [`checkpoint-dev.md`](prompts/checkpoint-dev.md) | Software / automation projects (code, architecture, infra) |
| [`checkpoint-design.md`](prompts/checkpoint-design.md) | Design & product work (flows, decisions, visual direction) |
| [`checkpoint-research.md`](prompts/checkpoint-research.md) | Research, analysis, long-form writing |
| [`resume.md`](prompts/resume.md) | Loading any checkpoint into a fresh chat |

A worked example lives in [`examples/`](examples/).

🇷🇺 Русская версия — в папке [`ru/`](ru/).

---

## 🧠 The idea in one picture

```
  Long chat (slow, expensive, hitting limits)
            │
            ▼
   [ paste checkpoint-dev.md ]
            │
            ▼
   Structured snapshot:
   • Goal       • Decisions + WHY
   • Architecture • What's done
   • Files changed • Known issues
   • Next step
            │
            ▼
   New chat  ──►  [ paste resume.md + snapshot ]
            │
            ▼
   Model is instantly up to speed.
   No re-explaining. No context loss.
```

---

## 💡 Why not just use the AI's memory?

Memory stores *who you are* over time ("works with n8n", "builds SaaS"). It does **not** store the *state of one specific project* — its architecture, the last 10 decisions, or what broke yesterday. That's exactly the gap a checkpoint fills.

---

## 🤝 Contributing

Got a checkpoint prompt that works great for your workflow? PRs welcome — add it under `prompts/` with a short note on when to use it.

## 📄 License

MIT — use it, fork it, ship it.

---

*If this saved you a re-explaining session, drop a ⭐ — it genuinely helps others find it.*
