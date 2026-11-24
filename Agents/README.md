# Agents

This folder describes **deployable IAGuardian research agents**: small, bounded helpers that gather public, cited information to support LTRCSMU (LTR).

Each agent is described by an **agent card**: a short plain-English file that says what the agent does, what it may read, what it may never do, and where its facts come from.

## What belongs here

- Agent cards (one file per agent) that are **publicly safe**.
- Links to public repositories that could help the agents, with license and attribution.
- Notes on how an agent should be run safely.

## What does not belong here

- Private repositories or private files
- Secrets of any kind (keys, seeds, tokens)
- Internal identifiers or private paths
- Third-party code without a license and credit

## Files

| File | What it is |
|---|---|
| [`AGENT_CARD_TEMPLATE.md`](AGENT_CARD_TEMPLATE.md) | Blank card. Copy it to describe a new agent. |
| [`examples/paper-trading-desk.md`](examples/paper-trading-desk.md) | Basic example: the IAGuardian paper-trading desk pattern. |

## Rules every agent card must follow

1. **Paper or testnet by default.**
2. **No stored private keys.** The agent never holds keys or signs transactions.
3. **A human approves** anything with real-world effect.
4. **Cite sources** and mark AI assistance (see [`../ATTRIBUTION.md`](../ATTRIBUTION.md)).
5. **No profit claims.**

> Educational only. Not financial advice. Use at your own risk.
