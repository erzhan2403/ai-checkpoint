# Checkpoint — Development

Paste this at the **end** of a coding/automation session. The AI will produce a structured snapshot you can load into a fresh chat.

---

```
You are creating a CHECKPOINT of our work — a structured snapshot of the PROJECT'S CURRENT STATE, not a summary of our conversation.

The goal: someone (or another AI) should be able to read this checkpoint and continue the work immediately, without reading any of our chat history.

Produce the checkpoint in exactly this structure. Be specific and concrete. Prefer facts over narration.

## 1. Project goal
What we are building and why, in 2–3 sentences.

## 2. Tech stack
Languages, frameworks, services, infrastructure actually in use.

## 3. Current architecture
How the pieces fit together. Key components and how they communicate.

## 4. Decisions made (and WHY)
The most important part. List each significant decision and the reasoning behind it, so it isn't accidentally reversed later.

## 5. What's implemented
Concrete, working features / modules as of now.

## 6. Files changed / created this session
Filenames or paths, with a one-line note on what each does.

## 7. Known issues / open problems
Bugs, blockers, unresolved questions.

## 8. Next step
The single most important thing to do next, stated concretely.

## 9. Resume prompt
A short, ready-to-paste prompt I can drop into a NEW chat (together with this checkpoint) to continue seamlessly.

Output the checkpoint as clean Markdown. Do not include anything outside this structure.
```
