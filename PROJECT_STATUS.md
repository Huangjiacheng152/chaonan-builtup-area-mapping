# Project Status

**Last updated:** 2026-10-25  
**Current phase:** Phase 1 — Data feasibility validation  
**Overall status:** The AreaCity archive has been downloaded by the user, extracted and checked; the Chaonan District polygon record is present and passes basic geometry validity checks. However, data-specific reuse terms and the GCJ-02 coordinate issue still need resolution. No complete set of 11 town-level polygons has yet been confirmed.

## Workstream status

| ID | Item | Status | Evidence / next action |
|---|---|---|---|
| ADMIN-01 | Chaonan District boundary | Downloaded and basic geometry checks passed; final suitability pending | Record ID 440514, path 广东省 汕头市 潮南区; 788 coordinate pairs; valid Polygon. Source CRS is GCJ-02. Data source is documented, but repository MIT licence does not by itself settle the licence of the underlying map geometries. See docs/AREA_CITY_CHAONAN_QA.md. |
| ADMIN-02 | All 11 town-level boundaries | Not confirmed | GeoJSONcn advertises free township/street downloads in WGS84, but actual Chaonan coverage, geometry integrity and licence terms have not been verified. OSM has a Chaonan District relation; the 11 subarea relations remain unconfirmed. See docs/FREE_TOWNSHIP_BOUNDARY_RESEARCH.md. |
| OSM-01 | Guangdong OSM extract | Candidate identified; not downloaded/inspected | Geofabrik provides a free regional extract; inspect whether it contains all 11 suitable town-level relations. |
| GHSL-01 | GHSL built-up product | Candidate identified | Select exact product/epoch; test download and inspect coverage and metadata |
| GHSL-02 | GHSL built surface product | Candidate identified | Verify product metadata, resolution, year and access |
| WC-01 | ESA WorldCover | Candidate identified | Test download and use as a cross-check if appropriate |
| DATA-01 | Data manifest | Partially updated | District file checked; remaining sources require actual validation |
| QA-01 | Reusable validation script | Pending | Add after the source formats and required libraries are confirmed |

## Immediate next actions

1. Test whether GeoJSONcn actually exposes all 11 Chaonan town/street polygons for free; download a vector format and inspect feature count, CRS, validity, parentage, extent and gaps/overlaps.
2. Query OSM/Overpass for all 11 names and inspect the actual relations and geometries; do not equate the known district relation with complete township coverage.
3. Resolve data-specific licence/provenance for any candidate intended for publication or redistribution.
4. Select and validate one built-up dataset.
5. Do not start final area calculations or map production until Phase 1 exit criteria in PROJECT_PLAN.md are satisfied.
