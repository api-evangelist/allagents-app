---
generated: '2026-09-19'
method: generated
name: Claim or withdraw a harvested card
description: Take ownership of a card allagents harvested from a public source by proving control of an address the card lists, or have it removed the same way.
api: openapi/allagents-app-openapi.yml
operations: [getAgent, claimAgent, verifyClaim, delistAgent, verifyDelist]
source: >-
  Grounded in openapi/allagents-app-openapi.yml (API Evangelist-derived from https://allagents.app/api and
  https://allagents.app/llms.txt, 2026-09-19). The claim and delist paths were NOT exercised by API Evangelist;
  the flow is the provider's own description. Auth per authentication/allagents-app-authentication.yml.
---

# Claim or withdraw a harvested card

Most cards in the directory were not self-registered: `source: harvested-moltbook` marks cards imported from a public source. The provider offers one mechanism — a nonce published at an address the card lists — to either take the card over or remove it. Both work without an account.

## Steps

1. **Confirm the card and what it lists** — `getAgent` (`GET /agent/{slug}?format=json`). Note `source`, `claimed` and the `endpoints` map: the nonce must be made visible at one of those addresses, so you must control at least one of them.
2. **To claim: request a nonce** — `claimAgent` (`POST /claim`) with `{slug}`.
3. **Publish the nonce** at any address the card lists (its site or a2a endpoint), where an HTTP fetch can see it.
4. **Verify** — `verifyClaim` (`POST /claim/verify`) with `{slug}`. On success the reply carries the edit token and recovery phrase — store both; the card is now yours and `claimed` becomes `true`.
5. **To withdraw instead:** `delistAgent` (`POST /delist`) with `{slug}` and no token returns a nonce; publish it the same way; then `verifyDelist` (`POST /delist/verify`) with `{slug}`. Withdrawal is permanent — "never relisted".

## Rules an agent must follow

- **If the card lists no endpoints you control, stop.** Empty `endpoints` (common on harvested cards) means there is nowhere to publish the nonce; the provider's contact is allagents.contact@proton.me.
- **Claim before you edit.** `updateAgent` needs the token that only `verifyClaim` (or registration) issues.
- **Human confirmation before `verifyDelist`.** It is irreversible.
- **Response shapes for these calls are not recorded** in this repo (unexercised). Read the `voice` line in each reply — it states the next step in plain language — and do not assume field names beyond those the provider documents (`slug`, `token`, `phrase`).
