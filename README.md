# Apple CloudKit (cloudkit)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Apple CloudKit is the cloud backend for iOS, iPadOS, macOS, tvOS, watchOS, visionOS, and the web. CloudKit Web Services is the public REST surface that lets non-Apple-platform clients (web apps, servers) read and write data into a CloudKit container's public, private, or shared database. The web service is hosted at api.apple-cloudkit.com and accepts either an API token (for end-user-authenticated access) or a server-to- server ECDSA key for backend access. Operations cover records, zones, subscriptions, assets, users, and database changes.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/cloudkit/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cloudkit/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Apple
- Cloud Storage
- CloudKit
- Database
- iCloud
- Mobile
- Sync
- Web Services

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-04-25

## APIs

### CloudKit Web Services

The CloudKit Web Services REST API is structured as /database/1/{container}/{environment}/{database}/{operation}, where database is one of public, private, or shared and environment is development or production. Operations include records lookup, query, modify, delete, zone create/list/delete, subscription create/list/delete, asset upload, user info and changes. Calls are authenticated using an API token for user-authenticated access (with ckWebAuthToken) or a server-to-server ECDSA key for backend access.

- **Human URL:** [https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/index.html](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/index.html)
- **Base URL:** `https://api.apple-cloudkit.com/database/1`

#### Tags

- REST
- Records
- Zones
- Subscriptions

#### Properties

- [Documentation](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/index.html)
- [Setup](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/SettingUpWebServices.html)
- [A P I  Tokens](https://developer.apple.com/documentation/cloudkit/obtaining-an-api-token-for-an-icloud-container)
- [Postman Collection](collections/cloudkit.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cloudkit.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CloudKit JS

CloudKit JS is Apple's JavaScript SDK that wraps the CloudKit Web Services REST API for browser apps. It provides Sign in with Apple authentication, container/database/zone access, queries, record operations, subscriptions, and asset management.

- **Human URL:** [https://developer.apple.com/documentation/cloudkitjs](https://developer.apple.com/documentation/cloudkitjs)

#### Tags

- JavaScript
- SDK
- Web

#### Properties

- [Documentation](https://developer.apple.com/documentation/cloudkitjs)
- [Postman Collection](collections/cloudkit.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cloudkit.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### CloudKit Framework

The native CloudKit framework for iOS, iPadOS, macOS, tvOS, watchOS, and visionOS. Provides programmatic access to CloudKit containers, records, zones, subscriptions, and sharing. Out of band of the web services REST surface but shares the same data model.

- **Human URL:** [https://developer.apple.com/documentation/cloudkit](https://developer.apple.com/documentation/cloudkit)

#### Tags

- SDK
- Apple Platforms

#### Properties

- [Documentation](https://developer.apple.com/documentation/cloudkit)
- [Postman Collection](collections/cloudkit.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cloudkit.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.icloud.com/)
- [Developer](https://developer.apple.com/icloud/cloudkit/)
- [Documentation](https://developer.apple.com/documentation/cloudkit)
- [Console](https://icloud.developer.apple.com/dashboard/)
- [Privacy Policy](https://www.apple.com/legal/privacy/)
- [JSON-LD](json-ld/cloudkit-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Spectral Rules](rules/cloudkit-rules.yml) — [Spectral](https://docs.stoplight.io/docs/spectral)

## Maintainers

**FN:** Kin Lane
**Email:** kinlane@gmail.com
