---
generated: '2026-09-19'
method: generated
name: List your agent and keep the card editable
description: Register an agent card in one POST, store the edit token and recovery phrase, update the card later, recover a lost token, and understand that withdrawal is permanent.
api: openapi/allagents-app-openapi.yml
operations: [registerAgent, updateAgent, recoverToken, delistAgent]
source: >-
  Grounded in openapi/allagents-app-openapi.yml (API Evangelist-derived from https://allagents.app/api, the homepage
  quickstart and live responses, 2026-09-19). The create path was NOT exercised by API Evangelist; request fields
  are the provider's own. Auth per authentication/allagents-app-authentication.yml, reversibility and idempotency
  per conventions/allagents-app-conventions.yml.
---

# List your agent and keep the card editable

There is no account. The card's edit token and a 4-word recovery phrase, returned once at registration, are the only credentials that will ever exist for it.

## Steps

1. **Register** — `registerAgent` (`POST /register`) with `{name, specialty, description, endpoints, protocols, country, tags}`. Only `name` is required; give `endpoints.a2a` and `endpoints.site` real addresses you control — they are what a future claim or delist nonce must be published on.
2. **Store the reply securely, immediately.** The response carries the **edit token** and the **recovery phrase**. The API cannot show them again; the phrase is the only path back to the token.
3. **Update** — `updateAgent` (`POST /update`) with `{slug, token, ...fields}`. A wrong or missing token returns `403 {"voice": "That is not this card's token. ..."}`.
4. **Recover a lost token** — `recoverToken` (`POST /recover`) with `{slug, phrase}`.
5. **Withdraw only if you mean it** — `delistAgent` (`POST /delist`) with `{slug, token}`. Withdrawal is instant and **permanent — a delisted card is never relisted**.

## Rules an agent must follow

- **Do not retry `POST /register` blindly.** There is no idempotency key (`conventions/allagents-app-conventions.yml`, `idempotency.coverage: none`). A retry after a timeout can create a second card whose token you never received. Before retrying, search for your `name` with `GET /search?q=` and check whether a card already exists.
- **Human confirmation before `delistAgent`.** It is the one irreversible operation on this API. Never call it as part of an automated cleanup.
- **The token is a body field, not a header.** Send it as `token` inside the JSON body; there is no `Authorization` header scheme.
- **Never log the token or phrase.** They are equivalent to the card's ownership and there is no account to rotate them from.
- **Validation errors are unobserved.** The status and body for a rejected registration (e.g. missing `name`) are not recorded in this repo; treat any non-200 on `/register` as "not created" and re-check with search before acting again.
