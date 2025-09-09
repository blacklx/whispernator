# Whispernator — Personal DM Translator Bot

A minimal, **DM-focused** translator for Discord. Whispernator runs via **message context menu** commands and replies **ephemerally** (only visible to you) right where you clicked — in **1:1 DMs** and **Group DMs**. No databases, no queues, no server admin features.

## Features
- **Message Context Menu (DMs & GDMs)**
  - **Translate — My Language**: uses your Discord app language (`interaction.locale`) to pick the target automatically.
  - **Translate — Choose Language**: shows an ephemeral dropdown of common, **Google-supported** languages.
- **Private by default**: replies are **ephemeral** via interaction flags, so only you can see them in the same chat.
- **Clean output**: translation shown as a **boxed code block inside an embed** for readability.
- **No DB**: uses a tiny **in-memory token store** only to link “Choose Language” selections for a short time.
- **TypeScript + discord.js v14** with a thin service around **Google Cloud Translation API v3**.
- **Minimal logging** with pino (no message content written to logs).

## Supported Languages (short list)
The dropdown only includes languages supported by Google Cloud Translation v3

Default list in the bot:
`en, es, pt, fr, de, it, nl, pl, ru, tr, ja, ko, zh, zh-TW, no, da, fi, sv, cs, el, hu, ro, uk, ar, he`

> You can customize the list in `src/utils/languageMap.ts`.
