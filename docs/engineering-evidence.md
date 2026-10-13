# KOWLO: selected engineering evidence

This page explains two retained development units behind the product case study. The records were inspected for this presentation on 13 October 2026. Application tests were not rerun during this documentation update, and the public showcase does not include the private application source or test harnesses.

## District classification and meaningful progress

**Product problem:** photo GPS should support district grouping without overstating where someone has been. Repeated photos in one district should not inflate progress, and a point on an ambiguous boundary should not receive an automatic district award.

**Implementation:** browser classification and the PostgreSQL/PostGIS foundation use the same pinned Home Affairs Department boundary data. Original coordinates, boundary relations and derived district progress remain distinct from the decorative atlas and suggested locality names.

**Retained result:** the browser/PostGIS parity record, generated at **2026-09-05T19:30:54.122Z**, reports agreement on **684 geographic controls**, including full match lists, names, boundary relations, statuses, source hashes and milestone IDs. The associated migration/database unit reports **209 checks passed** on PostgreSQL 18.4 / PostGIS 3.6.4.

The scenarios include four photos in Central counting as one district, adding Sha Tin increasing the count to two, editing that coordinate back to Central returning the count to one, and an empty journal counting zero. Database checks cover coordinate edits, record ownership isolation and restrictions on forged geometry.

The geographic controls are derived from the reference geometry. They establish consistency with that dataset; they do not establish GPS sensor accuracy, venue attendance or surveyed ground truth. This local unit did not verify live hosted Supabase authentication or production sync.

## Portable journal records

**Product problem:** a journal should preserve a person's records when they export them, including uncertainty about capture times and notes whose location record has been removed.

**Implementation:** JSON and GeoJSON downloads are prepared from the same atomic IndexedDB snapshot. Export field selection preserves coordinates, IDs, notes and capture-time states while excluding photo bytes, filenames and unrelated metadata. A retained note without a location exports with null geometry rather than an invented coordinate.

**Retained result:** the export unit records **41 passing Node checks**, including **200 deterministic generated snapshot cases**. The 200 cases are generated inputs within the checks, not 200 separate tests. Actual Chromium downloads were read back and compared with saved records. Downloads also succeeded with the local server stopped and the browser offline.

This record concerns the local diagnostic export foundation. It does not establish a restore/import feature, completed sharing on a physical phone, third-party GIS compatibility or equivalent behaviour in every later interface version.

## Provenance

The private development records retained for these summaries are `district-browser-postgis-parity.md`, `district-browser-postgis-parity.json`, `district-postgis-results.json` and `journal-geojson-export.md`.

The district reference comes from the [Home Affairs Department's 18-district boundary dataset](https://www.had.gov.hk/psi/hong-kong-administrative-boundaries/hksar_18_district_boundary.json). The parity record pins its SHA-256 as:

```text
e145cc41230d8215dfb0a797230a0c9671827c018ba608bfc3086966da4735c8
```

The public repository contains a curated explanation, not a reproducible source release or an independently audited performance report. No user adoption, retention or commercial outcome is inferred from these checks.

[Back to the product case study](../README.md) · [Credits and data terms](../CREDITS.md)
