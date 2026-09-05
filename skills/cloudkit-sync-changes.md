---
name: cloudkit-sync-changes
description: Incrementally sync a CloudKit database with sync tokens — database changes, zone changes and record changes — without re-reading everything.
api: cloudkit:cloudkit-changes-api
operations:
  - databaseChanges
  - zoneRecordChanges
  - zoneChanges
  - recordChanges
  - listZones
generated: '2026-09-05'
method: generated
source: openapi/cloudkit-changes-api-openapi.yml, openapi/cloudkit-zones-api-openapi.yml + https://developer.apple.com/library/archive/documentation/DataManagement/Conceptual/CloudKitWebServicesReference/FetchingDatabaseChanges(changeszone).html
---

# Sync CloudKit changes incrementally

Read-only. The whole point is to avoid re-querying a database you already have.

## The two tokens

CloudKit hands out two different change tokens and they are not interchangeable:

- `syncToken` — a position in a **zone's or database's** change history. This is what drives the
  operations in this skill.
- `recordChangeTag` — a version stamp on a **single record**, used on writes. See
  `cloudkit-modify-records`.

## Order of operations

1. `POST /changes/database` (`databaseChanges`) with the last `syncToken` you stored, or none on first
   run. It returns which zones changed, plus a new `syncToken`.
2. For each changed zone, `POST /changes/zone` (`zoneRecordChanges`) with that zone's stored
   `syncToken`. It returns the changed and deleted records and a new per-zone token.
3. Persist every returned `syncToken` **only after** you have durably applied the batch. A token stored
   before the work lands means silently skipped changes.

`POST /zones/changes` (`zoneChanges`) and `POST /records/changes` (`recordChanges`) cover the same
ground at zone and record granularity; pick one level and stay on it.

## Deletions

Deleted records come back with `"deleted": true` rather than disappearing — handle that flag or your
local copy will keep records the server no longer has.

## Paging and limits

Responses cap at 200 records. When more remain, keep calling with the returned marker/token until the
server stops handing one back.

## When a token is rejected

An expired or unknown `syncToken` means your position is no longer in the server's history. Recover by
re-listing zones (`listZones`) and doing a full read with `queryRecords`, then start a fresh token.
Never fabricate a token.

## Errors

`ZONE_NOT_FOUND` 404 (a zone was deleted between runs — drop your local copy of it), `THROTTLED` 429
(back off by `retryAfter` in the body), `TRY_AGAIN_LATER` 503. See `errors/cloudkit-problem-types.yml`.
