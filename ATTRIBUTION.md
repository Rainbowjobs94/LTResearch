# Attribution, Ownership, and Citation Rules

## Ownership notice (owner's claim)

The names and marks **LTIP (Lifetime Brand Trademark And Network)**, **LTRCSMU / LTR**, **Love Transcends**, **IAGuardian**, **QuantumChain**, **Miracle Network**, and related brand names are claimed by their owner (Love Transcends, the project owner), as brand names with long-term ownership.

This is the owner's claim of ownership. It is **not** a statement that any of these names is a registered trademark. No registration is asserted here.

The license in [`LICENSE`](LICENSE) covers the written content in this repo. **It does not grant any right to use the brand names, logos, or marks.** Ask the owner first.

## Rule 1: Cite every source

Every finding, claim, number, or quote needs a source: a link, a title, an author or owner, and the date you checked it. If you cannot cite it, label it **unverified** or leave it out.

## Rule 2: Mark AI assistance

- If AI produced **51% or more** of a finding, mark `ai-assisted: yes`.
- If AI helped but produced **less than 51%**, mark `ai-assisted: partial`. Marking is optional but welcome.
- If no AI was used, `ai-assisted: no`.

You do not have to label something fully "AI" if AI wrote less than half of it. When unsure, mark it.

Name the tool if you can (for example: "drafted with an AI assistant, reviewed and edited by a human").

## Rule 3: Third-party material

- Only include third-party code or text if its license allows it. Name the license and link to the source.
- Do not copy private repositories, paid content, or anything you do not have the right to share.
- Link to outside work instead of copying it whenever possible.

## Front-matter template

Put this at the top of any new guide or finding:

```yaml
---
title: Short plain title
author: Your name or handle
date: YYYY-MM-DD
status: draft | verified | unverified
ai-assisted: yes | no | partial
ai-tool: (optional) name of the tool used
sources:
  - title: Source name
    url: https://example.com
    owner: Who published it
    license: e.g. MIT, Apache-2.0, CC BY 4.0, unknown
    checked: YYYY-MM-DD
---
```

## Citation template (inline)

```
[Title of source](https://link) - Owner/author - License - checked YYYY-MM-DD
```

## Not allowed anywhere in this repo

Private keys, seed phrases, API keys, bot tokens, wallet addresses tied to real funds, private file paths, internal identifiers, personal data, or any claim of guaranteed profit.
