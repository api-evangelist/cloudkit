---
name: cloudkit-upload-assets
description: Upload a binary asset to CloudKit and attach it to a record — the two-step upload-URL flow, size cap, and how to reuse an existing asset.
api: cloudkit:cloudkit-assets-api
operations:
  - uploadAssets
  - rereferenceAssets
  - modifyRecords
generated: '2026-09-05'
method: generated
source: openapi/cloudkit-assets-api-openapi.yml + https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/UploadAssets.html
---

# Upload a CloudKit asset

Writes. An asset that has been attached to a record can only be removed by changing the record field —
there is no asset-delete operation.

## Step 1 — ask for an upload URL (`uploadAssets`)

POST `/assets/upload` naming the record type, the field the asset will live in, and the zone:

```json
{ "tokens": [ { "recordType": "Photo", "fieldName": "image", "recordName": "photo-1" } ],
  "zoneID": { "zoneName": "_defaultZone" } }
```

Up to 200 tokens per request. The response carries a one-shot `url` per token.

## Step 2 — POST the bytes to that URL

Send the file body to the returned URL. The response contains a **file reference dictionary** — keep it
verbatim; it is the only thing that binds the uploaded bytes to a record.

## Step 3 — attach it (`modifyRecords`)

Write the file reference into the record's asset field with `/records/modify`, following the
`cloudkit-modify-records` rules (current `recordChangeTag`, 200-operation batches, no idempotency key).
An asset that is never attached is not reachable.

## Reuse instead of re-uploading (`rereferenceAssets`)

`POST /assets/rereference` points an already-uploaded asset at another record — cheaper than uploading
the same bytes twice, and the right move when copying content between records.

## Limits

- Maximum asset file size: **50 MB**
- The record itself, excluding assets, caps at 1 MB
- Exceeding the app's public-database quota or the user's private iCloud storage returns
  `QUOTA_EXCEEDED` (413)

## Errors

`BAD_REQUEST` 400 (field is not an ASSET field, or the record type has no such field), `ACCESS_DENIED`
403, `NOT_FOUND` 404, `THROTTLED` 429. See `errors/cloudkit-problem-types.yml`.
