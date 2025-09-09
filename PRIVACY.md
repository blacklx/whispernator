
---

### `PRIVACY.md`
```markdown
# Privacy Policy — Whispernator (Personal DM Translator Bot)

_Last updated: 2025-09-09_

Whispernator is a personal translator for Discord messages. It is designed for privacy and simplicity: no databases, no analytics, and minimal logging.

## Summary
- **What we process:** Only the text you explicitly choose to translate, plus minimal technical metadata.
- **Where it goes:** The text you select is sent to **Google Cloud Translation API (v3)** to perform the translation.
- **What we store:** We do **not** store message content. Logs contain only non-content metadata (timestamps, status/error codes).
- **Visibility:** Replies are **ephemeral** interaction messages—only visible to the user who triggered the command—even in 1:1 DMs and Group DMs.

## Data We Process
### 1) Message content you select
- **Input:** The text of the message you right-click and choose to translate.
- **Purpose:** Provide the translation requested.
- **Storage:** Not persisted. Held in memory only long enough to complete the request.

### 2) Technical metadata
- Examples: timestamps, which command was used, success/failure, and message **length** (not the message text).
- Purpose: reliability, debugging, and abuse prevention.
- Storage: application logs (no message content).

### 3) Transient interaction state
- For the “Choose Language” menu, an in-memory record ties your selection to the original message (your Discord user ID, a short token, and a timestamp).
- Auto-swept after a short period (default ~1 hour). Never written to disk.

## Third Parties & Transfers
- **Discord** — provides the interaction payload (includes the selected message content).
- **Google Cloud Translation API (v3)** — processes the text to translate.
- The text you submit may be processed by Google in jurisdictions outside your country/region under Google’s enterprise terms and safeguards.

## Legal Bases (EEA/UK)
- **Performance of a contract / requested service:** translating the text you selected.
- **Legitimate interests:** service reliability and abuse prevention (limited to non-content metadata).

## Retention
- **Message content:** not stored.
- **Interaction state tokens:** in memory only; auto-deleted (~1 hour).
- **Logs (non-content metadata):** retained for up to **30 days** and then rotated. You may request earlier deletion of log entries if they include identifiers that concern you.

## Security
- TLS for all calls to Google APIs.
- Principle of least privilege for service account credentials.
- Minimal logs; no message content persisted.

## Your Choices & Rights
- Do not use the bot if you do not want to send text for translation.
- EEA/UK users may have rights to access, rectify, erase, or restrict processing of personal data (typically log identifiers, since we don’t store message content). Contact us to exercise rights.

## Children
- Whispernator follows Discord’s minimum age requirements; do not use the bot if you are under Discord’s minimum age in your region.

## Changes
We may update this policy. Material changes will be noted in the repository changelog.

## Contact
Questions or requests: **your-email@example.com**
