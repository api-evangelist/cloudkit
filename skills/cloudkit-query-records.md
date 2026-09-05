---
name: cloudkit-query-records
description: Query and page through records in a CloudKit database over CloudKit Web Services, using cursor pagination and field selection.
api: cloudkit:cloudkit-records-api
operations:
  - queryRecords
  - lookupRecords
generated: '2026-09-05'
method: generated
source: openapi/cloudkit-records-api-openapi.yml + https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/QueryingRecords.html
---

# Query CloudKit records

Read-only. Nothing in this skill writes.

## Build the URL

```
https://api.apple-cloudkit.com/database/1/{container}/{environment}/{database}/records/query
```

- `{container}` starts with `iCloud.` — e.g. `iCloud.com.example.app`
- `{environment}` is `development` or `production`. **This is the only thing separating test from live.** Check it before every call.
- `{database}` is `public`, `private` or `shared`

## Authenticate

Append `?ckAPIToken=<token>` for app-level access, and `&ckWebAuthToken=<token>` when acting for a
signed-in user. For a backend, sign instead — see `authentication/cloudkit-authentication.yml` — and do
**not** send `ckAPIToken` on a signed request; Apple states it will fail.

If the response is `AUTHENTICATION_REQUIRED` (HTTP 421), the body carries a `redirectURL`. A human must
open it and complete Apple's sign-in; you cannot mint a `ckWebAuthToken` yourself. Stop and surface the
URL rather than retrying.

## Query (`queryRecords`)

POST a JSON body:

```json
{
  "zoneID": { "zoneName": "myCustomZone" },
  "query": {
    "recordType": "myRecordType",
    "filterBy": [ { "systemFieldName": "createdUserRecordName", "comparator": "EQUALS",
                    "fieldValue": { "value": { "recordName": "recordA" }, "type": "REFERENCE" } } ],
    "sortBy": [ { "systemFieldName": "createdTimestamp", "ascending": false } ]
  },
  "resultsLimit": 200,
  "desiredKeys": ["title", "updatedAt"]
}
```

- `zoneWide: true` searches all zones; it is ignored when `zoneID` is set
- `desiredKeys` limits returned fields — use it, responses cap at 200 records
- `numbersAsStrings: true` if you need exact large numbers

## Page

If the response contains `continuationMarker`, more results exist. Re-POST the **same** query with
`"continuationMarker": "<value>"` added. Stop when no marker comes back. Never assume a page count.

## Fetch by name (`lookupRecords`)

POST `/records/lookup` with `{"records":[{"recordName":"..."}], "zoneID": {...}}` when you already hold
record names — cheaper and exact.

## Errors to expect

`ACCESS_DENIED` 403 (wrong database or missing role), `NOT_FOUND` 404, `ZONE_NOT_FOUND` 404,
`THROTTLED` 429 — back off by the `retryAfter` seconds in the body, there is no rate-limit header —
`TRY_AGAIN_LATER` 503. Full list in `errors/cloudkit-problem-types.yml`.

Queries with no filter require a Queryable index on `___recordID`, and any filtered field needs its own
Queryable index. A missing index shows up as a `BAD_REQUEST`, not as an empty result.
