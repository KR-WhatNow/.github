<div align="center">

**English** | [한국어](./README.ko.md) | [日本語](./README.ja.md)

# WhatNow

### Something broke. What now?

**Your AI can fix it. It just needs to know what happened.**

[Website](https://whatnow.dev)

</div>

---

## Don't explain your bug. Copy the context.

AI doesn't fail to fix your bug because it isn't smart enough.
It fails because it doesn't have the context.

**WhatNow is Ctrl+C for your AI.** When something breaks, it automatically collects everything your AI needs — git diff, stack trace, logs, terminal history, environment, Docker, Kubernetes — and packages it into the format AI understands best. One copy, one paste, fixed.

### Before

```text
Bug appears
  → Explain it to AI
  → "Please share your logs."
  → Paste logs
  → "Can I see application.yml?"
  → Paste config
  → "What did you change recently?"
  → Paste git diff
  → 40 minutes gone
```

### After

```text
Bug appears
  → Copy Context
  → Paste
  → Fixed
```

---

## How it works

```text
WHAT HAPPENED

14:32:17  You modified PaymentService.kt
14:33:02  Ran ./gradlew bootRun
14:33:04  MongoDB connection failed
14:33:05  Application startup failed

ROOT CAUSE

MongoDB authentication configuration
was changed in the latest commit.

[ Copy for Cursor ]  [ Copy for Claude ]  [ Copy for ChatGPT ]
```

We are not another AI. We are the program that organizes the incident into the shape your AI likes best.

> **Your AI is only as good as your context.**
