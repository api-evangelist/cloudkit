# Apple CloudKit (cloudkit)

Apple CloudKit is the cloud backend for iOS, iPadOS, macOS, tvOS, watchOS, visionOS, and the web. CloudKit Web Services is the public REST surface that lets non-Apple-platform clients (web apps, servers) read and write data into a CloudKit container's public, private, or shared database. The web service is hosted at `api.apple-cloudkit.com` and accepts either an API token (for end-user-authenticated access) or a server-to-server ECDSA key for backend access.

**APIs.json:** [apis.yml](https://raw.githubusercontent.com/api-evangelist/cloudkit/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **x-type:** company

## Tags

Apple, Cloud Storage, CloudKit, Database, iCloud, Mobile, Sync, Web Services

## APIs

### CloudKit Web Services
REST API at `https://api.apple-cloudkit.com/database/1/{container}/{environment}/{database}/{operation}` where `database` is `public`, `private`, or `shared` and `environment` is `development` or `production`. Operations include record lookup/query/modify/delete, zone create/list/delete, subscription management, asset upload, user info, and database changes.

- [Documentation](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/index.html)
- [Setup](https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/SettingUpWebServices.html)
- [API Tokens](https://developer.apple.com/documentation/cloudkit/obtaining-an-api-token-for-an-icloud-container)

### CloudKit JS
JavaScript SDK that wraps the CloudKit Web Services REST API for browser apps. Provides Sign in with Apple, container/database/zone access, queries, record operations, subscriptions, and asset management.

- [Documentation](https://developer.apple.com/documentation/cloudkitjs)

### CloudKit Framework
Native CloudKit framework for Apple platforms. Out of band of the web services REST surface but shares the same data model.

- [Documentation](https://developer.apple.com/documentation/cloudkit)

## Common Properties

- [Website](https://www.icloud.com/)
- [Developer Portal](https://developer.apple.com/icloud/cloudkit/)
- [CloudKit Console](https://icloud.developer.apple.com/dashboard/)
- [JSON-LD](json-ld/cloudkit-context.jsonld)
- [Spectral](rules/cloudkit-rules.yml)
- [Naftiko Capabilities](capabilities/cloudkit-records.yaml)

## Maintainers

- **FN:** Kin Lane
- **Email:** kinlane@gmail.com
