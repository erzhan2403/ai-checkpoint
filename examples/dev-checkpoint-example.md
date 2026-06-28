# Example — A Filled-In Dev Checkpoint

This is what a real checkpoint looks like after running `checkpoint-dev.md` on a project. Use it as a reference for the level of detail that makes checkpoints useful.

---

## 1. Project goal
A WhatsApp AI assistant for real estate agents that auto-replies to leads, qualifies them, and logs them to a CRM. Goal: let a single agent handle 5x the inbound volume without missing leads.

## 2. Tech stack
n8n (self-hosted), Evolution API v1.8.2 (WhatsApp), Supabase (Postgres), Claude Haiku (replies), Docker on a VPS.

## 3. Current architecture
WhatsApp message → Evolution API webhook → n8n workflow → bot-filter (Code node) → Claude Haiku for reply → send via Evolution API → log lead to Supabase. A Telegram bot toggles human/bot mode per conversation.

## 4. Decisions made (and WHY)
- **Bot filter uses a Code node returning `[]`, not an IF node** — IF nodes cached results and let messages leak through in human mode. Code node is deterministic.
- **Evolution API pinned to v1.8.2 + MongoDB** — v2.x was non-functional in testing.
- **Two separate "send" nodes** (one for commands, one for bot replies) — avoids routing collisions.

## 5. What's implemented
Auto-reply, lead logging to Supabase, per-conversation human/bot toggle, message filtering, typing presence.

## 6. Files changed / created this session
- `workflow-main.json` — added the Code-node bot filter
- `supabase/leads.sql` — leads table schema

## 7. Known issues / open problems
`sendPresence` endpoint returns an empty response, which fails the node — needs "Continue on Fail" enabled.

## 8. Next step
Add lead-qualification scoring (hot/warm/cold) based on message content before logging to Supabase.

## 9. Resume prompt
"Continuing the WhatsApp real-estate bot (n8n + Evolution API v1.8.2 + Supabase + Claude Haiku). Architecture and decisions are in the checkpoint. Next: add hot/warm/cold lead scoring before the Supabase log step."
