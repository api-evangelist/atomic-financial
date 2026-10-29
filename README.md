# Atomic

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

Atomic is the connected-banking infrastructure for income, payroll, and merchant data. Their user-permissioned APIs let banks, lenders, fintechs, and HR platforms link consumers to thousands of payroll providers, gig platforms, employers, and merchants — and then read or update that data in real time. Core use cases include direct-deposit switching, paycheck-linked income and employment verification, tax-document retrieval, and card-on-file / subscription management. Integration is done through the Transact SDK (web, iOS, Android, React Native, Flutter, Capacitor) plus a REST API at api.atomicfi.com that manages access tokens, tasks, companies, deposit accounts, and webhooks. Atomic is headquartered in Salt Lake City, Utah.

**Areas:** Income · Payroll · Direct Deposit · Employment Verification · Open Banking · Finance · Subscription · Bill Pay

## Atomic on APIs.io

Everything profiled for Atomic is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/atomic-financial/](https://apis.io/providers/atomic-financial/)** — or go straight to one of the APIs or properties below.

### APIs (7)

- [Atomic Deposit API](https://apis.io/apis/atomic-financial/atomic-deposit-api/) — Deposit (formerly Direct Deposit Switching) lets users redirect all or part of their paycheck to a new account. Atomic connects to thousands of payroll…
- [Atomic Verify API](https://apis.io/apis/atomic-financial/atomic-verify-api/) — Verify provides instant income and employment verification by connecting to the consumer's payroll provider or employer. Lenders, landlords, and fintechs…
- [Atomic PayLink API](https://apis.io/apis/atomic-financial/atomic-paylink-api/) — PayLink lets consumers update their card-on-file across merchants and subscription services. It is also the foundation for subscription discovery, bill…
- [Atomic Tax API](https://apis.io/apis/atomic-financial/atomic-tax-api/) — Tax retrieves W-2s, 1099s, and other tax documents directly from the user's payroll provider, and unlocks tax-refund use cases such as early-deposit and…
- [Atomic Authentication API](https://apis.io/apis/atomic-financial/atomic-authentication-api/) — Atomic's authentication layer powers user-permissioned access to third-party payroll, employer, and merchant systems. Three flavors are supported -…
- [Atomic Webhooks API](https://apis.io/apis/atomic-financial/atomic-webhooks-api/) — Atomic delivers task, company, and continuous-access events to your endpoint using the CloudEvents binary content mode. Events include task-status-updated,…
- [Atomic Transact SDK](https://apis.io/apis/atomic-financial/atomic-transact-sdk/) — The Transact SDK is the user-facing client that drives every Atomic flow — authentication, account selection, consent, and task execution. It ships as an…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/atomic-financial/](https://apis.io/graphqls/atomic-financial/atomic-financial-graphql/)

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Atomic Financial Domain Security](https://apis.io/security/atomic-financial/atomic-financial-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://atomic.financial/)
- [Documentation](https://docs.atomicfi.com/)
- [API reference](https://docs.atomicfi.com/reference/api)
- [Support](https://atomic.financial/help-center/)
- [Blog](https://atomic.financial/insights/)
- [GitHub](https://github.com/atomicfi)

## API Evangelist rating

**Kin Score 18.5** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 62.5 |
| Contract quality | 0.0 |
| Contract governance | 0.0 |
| Operational transparency | 10.5 |
| Developer ergonomics | 59.5 |
| Access clarity | 0.0 |

**Agent readiness 6.4** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | unknown |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 11.8** — Employment & Payroll

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/atomic-financial/](https://apis.io/providers/atomic-financial/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Atomic: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/atomic-financial/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
