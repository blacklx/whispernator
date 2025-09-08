# Privacy Policy — Whispernator (Personal DM Translator Bot)

_Last updated: 2025-09-08_

Whispernator is a personal translator for Discord messages. It works via **message context menu** commands and is intentionally minimal: no databases, no analytics, no user profiling.

## Summary
- **What we process:** Only the text you explicitly choose to translate, plus minimal technical metadata to deliver the reply.
- **Where it goes:** The selected text is sent to **Google Cloud Translation API (v3)** to perform the translation.
- **What we store:** No message content is stored server-side. Logs contain only non-content metadata (timestamps, errors) and are retained for a short period (see “Retention”).
- **Ephemeral replies:** In servers and group DMs, replies are ephemeral (only visible to the user who triggered the command). In 1:1 DMs, Discord does not support ephemerals; by default Whispernator **does not post** translations in 1:1 DMs to avoid exposing them to the other participant.

## Data We Process
### 1) Message content you select
- **Input:** The text of the message you right-click and choose “Translate”.
- **Purpose:** Provide the translation you requested.
- **Storage:** Not persisted. Held in memory briefly to complete your request.

### 2) Technical metadata
- Examples: timestamps, command name, success/failure, and the **length** of the translated text (not the text itself).
- Purpose: Reliability, debugging, and abuse prevention.
- Storage: Application logs (no message content).

### 3) Transient interaction state
- For the “Choose Language” menu, an in-memory record ties your selection to the original message (includes your Discord user ID, a short token, and a timestamp).
- Swept automatically (default ~1 hour); never written to disk.

## Third Parties & Data Transfers
- **Discord** — provides the interaction payload (including the selected message content).
- **Google Cloud Translation API (v3)** — processes the text to translate. By default Whispernator uses location `global`, which may involve processing in or outside your country/region.
- Your text may be transferred to and processed by Google in jurisdictions that may not provide the same level of data protection as your home country. We rely on Google’s enterprise terms and safeguards for cross-border transfers.

## Legal Bases (EEA/UK)
- **Performance of a contract / requested service:** to translate the text you selected.
- **Legitimate interests:** ensure security, prevent abuse, and improve reliability (limited to non-content metadata).

## Retention
- **Message content:** not stored.
- **Interaction state (language picker tokens):** in-memory only; auto-deleted (~1 hour).
- **Logs (non-content metadata):** retained for up to **30 days** for troubleshooting, then deleted or overwritten. You can ask us to purge earlier if logs contain identifiers that concern you.

## Security
- Transport encryption (HTTPS/TLS) to Google APIs.
- Principle of least privilege for service account credentials.
- No production database. Minimal logging without message content.

## Your Choices & Rights
- You can choose not to use the bot or not to submit text.
- If you are in the EEA/UK, you may have rights to access, rectify, or erase personal data, and to object or restrict certain processing. Since we don’t store message content, these rights typically apply to log identifiers (e.g., timestamps or user IDs associated with failures).
- Contact us to exercise rights or ask questions.

## Children
- Whispernator follows Discord’s minimum age requirements. Do not use the bot if you are below Discord’s minimum age for your region.

## Changes
We may update this policy from time to time. Material changes will be highlighted in the repository changelog.

## Contact
Questions or requests: **your-email@example.com**
