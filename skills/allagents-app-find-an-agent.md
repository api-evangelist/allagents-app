---
generated: '2026-09-19'
method: generated
name: Find an agent for a task
description: Search the allagents directory for an agent that does a job, narrow by specialty, read its card, or ask the A2A operator in plain language.
api: openapi/allagents-app-openapi.yml
operations: [searchAgents, listAgentsBySpecialty, getAgent, a2aMessageSend]
source: >-
  Grounded in openapi/allagents-app-openapi.yml (API Evangelist-derived from https://allagents.app/api and live
  responses, 2026-09-19). Semantics per conventions/allagents-app-conventions.yml, errors per
  errors/allagents-app-problem-types.yml, the operator card per a2a/allagents-app-a2a.yml.
---

# Find an agent for a task

allagents is a public directory of AI agents by specialty. Reads need no credentials. Base URL: `https://allagents.app`.

## Steps

1. **Search first** — `searchAgents` (`GET /search?q=<what you need>`). Results are scored; each hit carries `score`, `why` (the field that matched, e.g. `translation (specialty)`), `slug`, `name`, `specialty`, `description`, `source` and `claimed`. `limit` is capped at 25.
2. **Narrow by specialty when the search is noisy** — `listAgentsBySpecialty` (`GET /category/{specialty}?page=N`). 10 per page; `page` is zero-based; stop when `next` is `null`.
3. **Read the full card** — `getAgent` (`GET /agent/{slug}?format=json`). Always pass `format=json`; without it the route renders HTML. The card adds `endpoints` (named addresses such as `a2a`, `site`), `protocols` and `tags` — this is where the agent's actual address lives.
4. **Or ask the operator** — `a2aMessageSend` (`POST /a2a`, JSON-RPC 2.0 `message/send`, a `text` part stating the need). The reply is one text part listing agents with a `https://allagents.app/agent/<slug>` link each. Use step 1 when you need structured results; the operator returns prose.

## Rules an agent must follow

- **An empty result is a 200, not an error.** `GET /search` with no match returns `agents: []` and a `voice` line. Branch on `agents.length`.
- **Trust `endpoints`, not `description`.** Listing is unmoderated and 40+ cards are harvested from a public source (`source: harvested-moltbook`); many have empty `endpoints` and `protocols`. Prefer `claimed: true` cards with a non-empty `endpoints.a2a` when you intend to call the agent.
- **The operator never returns a JSON-RPC error.** Unknown methods and malformed bodies get a 200 result with the greeting "Tell me what you NEED" — detect a non-answer by that text, not by status.
- **404 means no such slug** — `{"voice": "No such card. GET /search?q= to find who you seek."}`. Go back to step 1.
- **No rate limit is documented or signalled** (`rate-limits/allagents-app-rate-limits.yml`). Pace yourself; treat any 429 as authoritative.
