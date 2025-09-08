# Whispernator — Personal DM Translator Bot


A minimal, DM-focused translator bot using **discord.js v14** and **Google Cloud Translate**.


## Core UX
- **Context menu commands** on any message:
- **Translate — My Language**: auto-detects your Discord app language (via `interaction.locale`) and translates the selected message.
- **Translate — Choose Language**: shows a dropdown of common languages.
- Replies are **ephemeral where supported** (in guilds). Discord does **not** support ephemeral messages in DMs; in DMs the translation will appear in the DM thread.
- No queues, no linking, no admin ops.


## Setup
1. **Discord application**
- Create a bot and invite with scopes `bot` and `applications.commands`.
- For DM usage, permissions are minimal; message content intent helps but the context menu provides content regardless. Enable **Message Content Intent** for best compatibility.
- Turn on **Enable in DMs** for the app commands.
2. **Google Cloud**
- Create a project and enable **Cloud Translation API**.
- Create a service account with role `Cloud Translation API User` and download the JSON key.
- Set `GOOGLE_PROJECT_ID` and `GOOGLE_APPLICATION_CREDENTIALS` in your environment.
3. **Environment**
- Copy `.env.example` → `.env` and fill the values.
4. **Install & run**
```bash
pnpm i # or npm i / yarn
pnpm run register # registers global commands
pnpm run dev # start in watch mode
# or build & run
pnpm run build && pnpm start
```


## Notes & Limitations
- **Ephemeral**: Only works in guilds. Discord does not support ephemeral interaction responses in DMs.
- **Attachments**: This starter handles only text content. Add OCR if needed.
- **Locales**: `interaction.locale` maps to Google codes via `utils/languageMap.ts`. Extend as desired.
- **No DB**: A tiny in-memory store links the select menu to the message text; it auto-sweeps.


## File map
See the repository tree at the top of this document for the full layout.
