# Project Status

**Last updated:** 2026-10-25  
**Current phase:** Phase 1 — Data feasibility validation  
**Overall status:** Repository initialized; data validation has not yet been completed.

## Workstream status

| ID | Item | Status | Evidence / next action |
|---|---|---|---|
| ADMIN-01 | Chaonan District boundary | Not verified | Find a public download source; download and inspect the file |
| ADMIN-02 | All 11 town-level boundaries | Not verified | Highest-priority dependency; verify coverage and names |
| OSM-01 | Guangdong OSM extract | Candidate identified | Download only after confirming suitable format; inspect actual coverage |
| GHSL-01 | GHSL built-up product | Candidate identified | Select exact product/epoch; test download and inspect |
| GHSL-02 | GHSL built surface product | Candidate identified | Verify product metadata, resolution, year and access |
| WC-01 | ESA WorldCover | Candidate identified | Test download and use only as a cross-check unless justified otherwise |
| DATA-01 | Data manifest | Pending | Create manifest after sources are checked |
| QA-01 | Reusable validation script | Pending | Add once test formats and libraries are known |

## Status definitions

- **Not verified:** no adequate source evidence or downloaded-file check yet.
- **Candidate identified:** a plausible public source is known, but the specific file has not been validated.
- **Downloaded:** the file has been retrieved successfully.
- **Validated:** technical checks have been performed and recorded.
- **Suitable:** the data meet the stated purpose and limitations are acceptable.

## Immediate next actions

1. Verify the administrative boundary source, especially the complete set of 11 town-level units.
2. Test one built-up data candidate end to end: access page → download → open → inspect coverage and metadata.
3. Record results in `data/manifests/source_register.csv`.
4. Do not start final area calculations or map production until Phase 1 exit criteria in `PROJECT_PLAN.md` are satisfied.
