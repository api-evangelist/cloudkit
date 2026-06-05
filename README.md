# Apple CloudKit (cloudkit)

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
