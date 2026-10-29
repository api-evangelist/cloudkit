# Apple CloudKit

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

Apple CloudKit is the cloud backend for iOS, iPadOS, macOS, tvOS, watchOS, visionOS, and the web. CloudKit Web Services is the public REST surface that lets non-Apple-platform clients (web apps, servers) read and write data into a CloudKit container's public, private, or shared database. The web service is hosted at api.apple-cloudkit.com and accepts either an API token (for end-user-authenticated access) or a server-to- server ECDSA key for backend access. Operations cover records, zones, subscriptions, assets, users, and database changes.

**Areas:** Apple · Cloud Storage · CloudKit · Database · iCloud · Mobile · Sync · Web Services

## Apple CloudKit on APIs.io

Everything profiled for Apple CloudKit is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/cloudkit/](https://apis.io/providers/cloudkit/)** — or go straight to one of the APIs or properties below.

### APIs (10)

- [CloudKit Web Services](https://apis.io/apis/cloudkit/web-services/) — The CloudKit Web Services REST API is structured as /database/1/{container}/{environment}/{database}/{operation}, where database is one of public, private,…
- [CloudKit JS](https://apis.io/apis/cloudkit/js/) — CloudKit JS is Apple's JavaScript SDK that wraps the CloudKit Web Services REST API for browser apps. It provides Sign in with Apple authentication,…
- [CloudKit Framework](https://apis.io/apis/cloudkit/framework/) — The native CloudKit framework for iOS, iPadOS, macOS, tvOS, watchOS, and visionOS. Provides programmatic access to CloudKit containers, records, zones,…
- [Apple CloudKit Assets API](https://apis.io/apis/cloudkit/cloudkit-assets-api/) — The Assets API from Apple CloudKit — 2 operation(s) for assets.
- [Apple CloudKit Changes API](https://apis.io/apis/cloudkit/cloudkit-changes-api/) — The Changes API from Apple CloudKit — 2 operation(s) for changes.
- [Apple CloudKit Records API](https://apis.io/apis/cloudkit/cloudkit-records-api/) — The Records API from Apple CloudKit — 6 operation(s) for records.
- [Apple CloudKit Subscriptions API](https://apis.io/apis/cloudkit/cloudkit-subscriptions-api/) — The Subscriptions API from Apple CloudKit — 3 operation(s) for subscriptions.
- [Apple CloudKit Tokens API](https://apis.io/apis/cloudkit/cloudkit-tokens-api/) — The Tokens API from Apple CloudKit — 2 operation(s) for tokens.
- [Apple CloudKit Users API](https://apis.io/apis/cloudkit/cloudkit-users-api/) — The Users API from Apple CloudKit — 4 operation(s) for users.
- [Apple CloudKit Zones API](https://apis.io/apis/cloudkit/cloudkit-zones-api/) — The Zones API from Apple CloudKit — 4 operation(s) for zones.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [cloudkit-web-services (candidate)](https://apis.io/servers/cloudkit/cloudkit-web-services-candidate/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Cloudkit Agentic Access](https://apis.io/agentic-access/cloudkit/cloudkit-agentic-access/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Cloudkit Context](https://apis.io/jsonld/cloudkit/cloudkit-context/)

#### Collections (8)

Postman and Open Collection request collections.

- [Apple CloudKit Web Services](https://apis.io/collections/cloudkit/open-cloudkit/)
- [Apple CloudKit Web Services Assets API](https://apis.io/collections/cloudkit/open-cloudkit-assets-api/)
- [Apple CloudKit Web Services Assets Changes API](https://apis.io/collections/cloudkit/open-cloudkit-changes-api/)
- [Apple CloudKit Web Services Assets Records API](https://apis.io/collections/cloudkit/open-cloudkit-records-api/)
- [Apple CloudKit Web Services Assets Subscriptions API](https://apis.io/collections/cloudkit/open-cloudkit-subscriptions-api/)
- [Apple CloudKit Web Services Assets Tokens API](https://apis.io/collections/cloudkit/open-cloudkit-tokens-api/)
- [Apple CloudKit Web Services Assets Users API](https://apis.io/collections/cloudkit/open-cloudkit-users-api/)
- [Apple CloudKit Web Services Assets Zones API](https://apis.io/collections/cloudkit/open-cloudkit-zones-api/)

#### Overlays (7)

OpenAPI overlays, including conversational phrasing for each operation.

- [Cloudkit Assets Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-assets-api-overlay/)
- [Cloudkit Changes Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-changes-api-overlay/)
- [Cloudkit Records Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-records-api-overlay/)
- [Cloudkit Subscriptions Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-subscriptions-api-overlay/)
- [Cloudkit Tokens Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-tokens-api-overlay/)
- [Cloudkit Users Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-users-api-overlay/)
- [Cloudkit Zones Api Overlay](https://apis.io/overlays/cloudkit/cloudkit-zones-api-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Apple CloudKit API Rules](https://apis.io/rules/cloudkit/cloudkit-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Cloudkit Authentication](https://apis.io/security/cloudkit/cloudkit-authentication/)
- [Cloudkit Domain Security](https://apis.io/security/cloudkit/cloudkit-domain-security/)
- [Cloudkit Trust Center](https://apis.io/security/cloudkit/cloudkit-trust-center/)
- [Cloudkit Vulnerability Disclosure](https://apis.io/security/cloudkit/cloudkit-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Cloudkit Plans Pricing](https://apis.io/plans/cloudkit/cloudkit-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Cloudkit Rate Limits](https://apis.io/rate-limits/cloudkit/cloudkit-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.icloud.com/)
- [Documentation](https://developer.apple.com/documentation/cloudkit)
- [Getting started](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/SettingUpWebServices.html)
- [API reference](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/index.html)
- [Pricing](https://developer.apple.com/programs/)
- [Sign up](https://developer.apple.com/programs/enroll/)
- [Support](https://developer.apple.com/support/)
- [Blog](https://developer.apple.com/news/)
- [Terms of service](https://www.apple.com/legal/internet-services/icloud/)
- [Privacy policy](https://www.apple.com/legal/privacy/)
- [GitHub](https://github.com/apple)

## API Evangelist rating

**Kin Score 61.7** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 46.9 |
| Contract governance | 31.8 |
| Operational transparency | 76.3 |
| Developer ergonomics | 80.4 |
| Access clarity | 60.5 |

**Agent readiness 25.2** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 35.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/cloudkit/](https://apis.io/providers/cloudkit/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Apple CloudKit: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/cloudkit/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
