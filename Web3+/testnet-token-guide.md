---
title: Create a test token on a public testnet
author: LTResearch maintainers
date: 2026-11-24
status: draft
ai-assisted: partial
sources:
  - title: SPL Token CLI docs
    url: https://spl.solana.com/token
    owner: Solana community
    license: see site
    checked: 2026-11-24
  - title: Solana documentation
    url: https://solana.com/docs
    owner: Solana Foundation
    license: see site
    checked: 2026-11-24
  - title: Solana devnet faucet
    url: https://faucet.solana.com
    owner: Solana Foundation
    license: n/a
    checked: 2026-11-24
---

# Create a test token on a public testnet

> **DRAFT. TESTNET ONLY. Use at your own risk.**
> Test tokens have **no value**. This guide does not explain how to buy any token on a main network, and nothing here is investment advice.
> Commands below were taken from the public docs linked above and were **not re-run for this draft**. Check the current docs; tools and options change.

## Labels

For LTR purposes, a token made with this guide on a public test network can be called a **QuantumChain / Miracle Network testnet token** while the project is in testing. For now it is simply a standard test token on **Solana devnet**. It is not a mainnet asset.

## What you need

- A computer with the Solana command-line tools and the `spl-token` CLI installed. See the docs linked above.
- A **brand-new, throwaway devnet keypair**. Never reuse a keypair that has ever held real funds.

## Steps

1. **Point the CLI at devnet.**
   ```
   solana config set --url devnet
   ```
2. **Create a throwaway keypair** and keep the file private. Never commit it, post it, or paste it into a chat.
   ```
   solana-keygen new --outfile devnet-test-keypair.json
   solana config set --keypair devnet-test-keypair.json
   ```
3. **Get free test SOL** from the devnet faucet (link above), or:
   ```
   solana airdrop 2
   ```
   The faucet may be rate-limited or ask for sign-in. Test SOL has no value.
4. **Create the token** (this prints the token's mint address).
   ```
   spl-token create-token
   ```
5. **Create a token account** for your wallet to hold it.
   ```
   spl-token create-account <MINT_ADDRESS>
   ```
6. **Mint some test tokens** to yourself.
   ```
   spl-token mint <MINT_ADDRESS> 1000
   ```
7. **Check the supply.**
   ```
   spl-token supply <MINT_ADDRESS>
   ```

## Safety notes

- Make sure the CLI says **devnet** before every command (`solana config get`).
- Add `devnet-test-keypair.json` (and any `*.json` keypair) to your `.gitignore`.
- Do not publish the keypair. Do not send real funds to it.
- Do not post a test token as if it were an investment. It has no value.

## Not covered (yet)

- Token name, symbol, and image (metadata)
- Any LTR-specific rules for a QuantumChain / Miracle Network token (the owner has not published them here)
- Anything on a main network

## Contributing
Re-run the steps on devnet, note the tool versions, and send a pull request with what changed. See [`how-to-contribute.md`](how-to-contribute.md).
