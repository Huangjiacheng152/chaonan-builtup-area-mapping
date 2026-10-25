# Project Status

**Last updated:** 2026-10-25  
**Current phase:** Phase 1 — Data feasibility validation  
**Overall status:** AreaCity district boundary archive has been uploaded by the user, extracted successfully, and the Chaonan District record has passed basic geometry validity checks. Township boundaries and built-up data are still unverified.

## Workstream status

| ID | Item | Status | Evidence / next action |
|---|---|---|---|
| ADMIN-01 | Chaonan District boundary | Downloaded and basic geometry checks passed; suitability not yet fully accepted | Record ID 440514, hierarchy path 广东省 汕头市 潮南区; 788 coordinate pairs; Shapely reports valid Polygon. Source coordinates are GCJ-02 and must not be treated as WGS84. See `docs/AREA_CITY_CHAONAN_QA.md`. |
| ADMIN-02 | All 11 town-level boundaries | No free complete polygon source confirmed | Investigate free OSM relations and other public sources; paid/approval-based options are not preferred |
| OSM-01 | Guangdong OSM extract | Candidate identified | Download only after confirming suitable format; inspect actual coverage |
| GHSL-01 | GHSL built-up product | Candidate identified | Select exact product/epoch; test download and inspect coverage |
| GHSL-02 | GHSL built surface product | Candidate identified | Verify product metadata, resolution, year and access |
| WC-01 | ESA WorldCover | Candidate identified | Test download and use only as a cross-check unless justified otherwise |
| DATA-01 | Data manifest | Partially updated | District archive checked; remaining sources still need actual validation |
| QA-01 | Reusable validation script | Pending | Add once test formats and libraries are known |

## Status definitions

- **Not verified:** no adequate source evidence or downloaded-file check yet.
- **Candidate identified:** a plausible public source is known, but the specific file has not been validated.
- **Downloaded:** the file has been retrieved successfully.
- **Validated:** technical checks have been performed and recorded.
- **Suitable:** the data meet the stated purpose and limitations are acceptable.

## Immediate next actions

1. Identify and validate a free, complete polygon source for the 11 town/street units.
2. Test one built-up data candidate end to end: access page → download → open → inspect coverage and metadata.
3. Review the AreaCity data-specific licence and coordinate conversion options before redistributing or using its geometry for final area calculations.
4. Do not start final area calculations or map production until Phase 1 exit criteria in `PROJECT_PLAN.md` are satisfied.
