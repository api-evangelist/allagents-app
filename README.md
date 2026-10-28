# allagents

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

allagents (allagents.app) is a public directory of AI agents by specialty, operated from Switzerland. It lists more than 6,000 agents across specialties such as trading, research, coding, memory, automation, legal, commerce, identity and security, each card carrying the agent's name, address, protocols and how to reach it. Listing is free, instant and account-less — one POST returns an edit token and a recovery phrase — and withdrawal is instant and permanent. The directory exposes a small JSON API (search, browse by page or specialty, one card, register, update, claim, recover, delist), publishes an llms.txt, and is itself an A2A agent: its conformant agent card at /.well-known/agent-card.json points at a JSON-RPC message/send operator that answers a plain-language need with matching agents.

**Areas:** Company · AI Agents · Agent Directory · A2A · Discovery · Search · Registry · Switzerland

## allagents on APIs.io

Everything profiled for allagents is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/allagents-app/](https://apis.io/providers/allagents-app/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [allagents Operator (A2A Agent)](https://apis.io/apis/allagents-app/allagents-operator-a2a-agent/) — The directory as an A2A agent. POST a JSON-RPC 2.0 message/send stating a need ("I need a translation agent") and the operator answers with ranked matching…
- [allagents Directory API](https://apis.io/apis/allagents-app/allagents-app-directory-api/) — Read the book — search, browse by page, browse by specialty, read one card.
- [allagents Discovery API](https://apis.io/apis/allagents-app/allagents-app-discovery-api/) — Machine-readable discovery documents.
- [allagents Listing API](https://apis.io/apis/allagents-app/allagents-app-listing-api/) — Create and manage your own agent card. No account; an edit token and a 4-word recovery phrase are returned on registration.
- [allagents Operator API](https://apis.io/apis/allagents-app/allagents-app-operator-api/) — The directory is itself an A2A agent (JSON-RPC 2.0, message/send) that answers a need in plain language with matching agents.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [allagents](https://apis.io/servers/allagents-app/allagents/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Allagents App Agentic Access](https://apis.io/agentic-access/allagents-app/allagents-app-agentic-access/)

#### JSON Schema (7)

The data models the API reads and writes.

- [AgentCardResponse](https://apis.io/schemas/allagents-app/allagents-app-agent-card-response/)
- [AgentPage](https://apis.io/schemas/allagents-app/allagents-app-agent-page/)
- [JsonRpcMessageResult](https://apis.io/schemas/allagents-app/allagents-app-json-rpc-message-result/)
- [JsonRpcMessageSendRequest](https://apis.io/schemas/allagents-app/allagents-app-json-rpc-message-send-request/)
- [RegisterRequest](https://apis.io/schemas/allagents-app/allagents-app-register-request/)
- [SearchResult](https://apis.io/schemas/allagents-app/allagents-app-search-result/)
- [SpecialtyPage](https://apis.io/schemas/allagents-app/allagents-app-specialty-page/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Allagents App Context](https://apis.io/jsonld/allagents-app/allagents-app-context/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Allagents App Directory Overlay](https://apis.io/overlays/allagents-app/allagents-app-directory-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [allagents API Rules](https://apis.io/rules/allagents-app/allagents-app-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Allagents App Authentication](https://apis.io/security/allagents-app/allagents-app-authentication/)
- [Allagents App Domain Security](https://apis.io/security/allagents-app/allagents-app-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Allagents App Plans Pricing](https://apis.io/plans/allagents-app/allagents-app-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Allagents App Rate Limits](https://apis.io/rate-limits/allagents-app/allagents-app-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://allagents.app/)
- [Documentation](https://allagents.app/api)
- [Getting started](https://allagents.app/)
- [API reference](https://allagents.app/api)
- [Pricing](https://allagents.app/)

## API Evangelist rating

**Kin Score 27.8** — thin · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 11.6 |
| Contract governance | 18.2 |
| Operational transparency | 0.0 |
| Developer ergonomics | 47.0 |
| Access clarity | 31.6 |

**Agent readiness 32.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 16.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/allagents-app/](https://apis.io/providers/allagents-app/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for allagents: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/allagents-app/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
