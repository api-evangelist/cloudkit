---
name: cloudkit-modify-records
description: Create, update and delete CloudKit records safely — batch limits, recordChangeTag concurrency, and the fact that deletes cannot be undone.
api: cloudkit:cloudkit-records-api
operations:
  - modifyRecords
  - lookupRecords
generated: '2026-09-05'
method: generated
source: openapi/cloudkit-records-api-openapi.yml + https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/ModifyRecords.html
---

# Modify CloudKit records

**Destructive. There is no undo.** CloudKit publishes no reversal, restore or trash operation. A record
deleted through this endpoint is gone as far as the API is concerned, and no retention window is
documented. Confirm with the human before any delete.

## Endpoint

POST `https://api.apple-cloudkit.com/database/1/{container}/{environment}/{database}/records/modify`

Double-check `{environment}`. The same credentials write to `development` or `production` depending on
one path segment.

## Body

```json
{
  "operations": [
    { "operationType": "create",  "record": { "recordType": "Note", "fields": { "title": { "value": "Hi" } } } },
    { "operationType": "update",  "record": { "recordName": "abc", "recordType": "Note",
                                              "recordChangeTag": "m1", "fields": { "title": { "value": "Hi 2" } } } },
    { "operationType": "delete",  "record": { "recordName": "def", "recordChangeTag": "m4" } }
  ],
  "zoneID": { "zoneName": "_defaultZone" },
  "atomic": false
}
```

- **Maximum 200 operations per request.** Chunk larger work.
- `update`, `replace` and `delete` require the current `recordChangeTag`. Fetch it with `lookupRecords`
  first; a stale tag returns `CONFLICT` (409), which is the API protecting you from a lost update.
- On `CONFLICT`: re-fetch, re-check that your change still makes sense, then retry. Do not loop blindly.

## Retries are not free

There is **no `Idempotency-Key`**. Retrying a `create` whose response you never saw creates a **second
record**. If a retry is possible, supply your own deterministic `recordName` in the create and treat
`EXISTS` (409) as "already done".

## Atomicity

In a zone created with `atomic: true`, any failed operation fails the whole batch with `ATOMIC_ERROR`
(400). In a non-atomic zone, results come back per operation — read every entry, not just the HTTP
status.

## Errors

`ACCESS_DENIED` 403, `BAD_REQUEST` 400, `CONFLICT` 409, `EXISTS` 409, `QUOTA_EXCEEDED` 413 (app quota on
public, the user's own iCloud storage on private), `VALIDATING_REFERENCE_ERROR` 412, `THROTTLED` 429
(back off by `retryAfter` in the body). See `errors/cloudkit-problem-types.yml`.

Record payloads cap at 1 MB excluding assets.
