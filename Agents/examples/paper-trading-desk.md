---
title: IAGuardian paper-trading desk (pattern)
author: LTResearch maintainers
date: 2026-11-24
status: draft
ai-assisted: partial
sources:
  - title: DexScreener API reference
    url: https://docs.dexscreener.com/api/reference
    owner: DexScreener
    license: see site terms (unverified)
    checked: 2026-11-24
  - title: RugCheck API
    url: https://api.rugcheck.xyz/swagger/index.html
    owner: RugCheck
    license: see site terms (unverified)
    checked: 2026-11-24
---

# Agent card: IAGuardian paper-trading desk (pattern)

> **PAPER ONLY. Educational. Not financial advice.** This is a design pattern, not a working product and not a promise of any result.

## Purpose
Show a safe order of checks for studying new tokens in simulation. The goal is to learn what filters work, not to earn.

## The pattern (in order)

1. **Code kills rugs first.** Plain code, not opinion, rejects a token if public facts look unsafe. Facts come from sources such as RugCheck and DexScreener (for example: liquidity, holder concentration, mint or freeze authority still enabled, very new pair).
2. **X read second.** Only tokens that survive step 1 get a read of public posts on X for context. If the read is skipped or fails, the result is **"review"**, never "pass".
3. **A human signs.** The agent never signs. Any real action is decided and signed by a person.
4. **Paper by default.** Entries are written to a simulated journal with a fixed small ticket size, a stop, and a cool-down before re-entry.

## Inputs (read-only)
- DexScreener public data
- RugCheck public report
- Public X posts (read only)

## Outputs
- A journal line per check: pass / reject / review, with the facts used and their sources.
- A short digest for a human to read.

## Rails
- No private keys held by the agent. None.
- No transaction signing, no wallet connection.
- Paper mode is the default. Going live is a separate human decision with a hard loss cap.
- A skipped or failed check can never turn into a buy.
- No posting, emailing, or messaging by the agent on its own.

## Human checkpoint
A person reads the digest and decides whether anything is worth studying further.

## Known limits
- Public data can be wrong, late, or manipulated.
- Passing the filters does not mean a token is safe or will go up.
- Source terms and rate limits for DexScreener and RugCheck are **unverified** here; check them before building.
