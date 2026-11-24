---
title: Read-only signals and notifications
author: LTResearch maintainers
date: 2026-11-24
status: draft
ai-assisted: partial
sources:
  - title: Telegram Bot API
    url: https://core.telegram.org/bots/api
    owner: Telegram
    license: see site
    checked: 2026-11-24
  - title: Telegram bot features (BotFather)
    url: https://core.telegram.org/bots/features#botfather
    owner: Telegram
    license: see site
    checked: 2026-11-24
  - title: DexScreener API reference
    url: https://docs.dexscreener.com/api/reference
    owner: DexScreener
    license: see site terms (unverified)
    checked: 2026-11-24
---

# Read-only signals and notifications

> **DRAFT. Educational. Not financial advice. Paper mode by default. No earnings claims.**
> Signals can be wrong, late, or manipulated. Trading can lose all your money.

## Goal
A bot or agent **reads** public market data and **sends a notification** to a human (for example "this paper rule says consider selling"). The human decides. The bot does nothing else.

## What this design is
- Read-only access to public market data (for example DexScreener's public API).
- Notifications sent to a chat, such as a **Telegram bot**.
- A **paper journal** that records what the rule said and what happened, so you can judge the rule without risking money.

## What this design is not
- It does **not** place, sign, or send any trade.
- It does **not** hold private keys, seed phrases, or exchange trading permissions.
- It does **not** promise or imply earnings.

## Rules (non-negotiable)

1. **Paper mode is the default.**
2. **A human signs every trade**, outside the bot, in their own wallet or account.
3. **No private keys stored** anywhere in the bot, its config, or this repo.
4. **Hard loss-cap principle.** Before any live experiment, the owner sets a small fixed amount they can afford to lose completely. The experiment stops when it is reached. No exceptions, no "one more try".
5. **Skipped or failed checks never become a buy signal.** If data is missing, the answer is "review".
6. **Read-only API keys only**, if any key is needed at all. Never a key that can trade or withdraw.

## How to set up a Telegram notification bot (outline)

1. In Telegram, open the official **BotFather** and create a bot with `/newbot`. See the BotFather link above.
2. BotFather gives you a **bot token**. Treat it like a password.
3. Store the token in an **environment variable or secrets manager**, never in code or in this repo.
4. Your bot sends messages with the Bot API's `sendMessage` method (see the Bot API link above) to a chat that you control.
5. Test with a harmless message such as "test notification" before connecting any market rule.

No code is included here on purpose. This repo contains no code that signs transactions or handles keys.

## Example message shape (paper)

```
[PAPER] Rule "example-rule" flagged TOKEN_X for REVIEW.
Facts: <cited facts and times>
No action taken. You decide.
```

## Known limits
- DexScreener's and others' terms, rate limits, and key requirements are **unverified** here. Check before building.
- Rules tested only on paper may behave differently in real markets.
