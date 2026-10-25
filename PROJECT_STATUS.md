# Project Status

**Last updated:** 2026-10-25  
**Current phase:** Phase 1 — Data feasibility validation  
**Overall status:** AreaCity district boundary archive has been extracted and basic geometry validity checked. GeoJSONcn's Chaonan page lists all 11 expected town/street units and claims the district export contains their polygon features, but a downloadable vector file has not been obtained or independently inspected. Download pricing/access statements on the site are inconsistent. No town-level geometry set is yet validated.

## Workstream status

| ID | Item | Status | Evidence / next action |
|---|---|---|---|
| ADMIN-01 | Chaonan District boundary | Downloaded and basic geometry checks passed; final suitability pending | Record ID 440514, path 广东省 汕头市 潮南区; 788 coordinate pairs; valid Polygon. Source CRS is GCJ-02. Data-specific reuse terms and coordinate handling still need resolution. See docs/AREA_CITY_CHAONAN_QA.md. |
| ADMIN-02 | All 11 town-level boundaries | Names/count confirmed on GeoJSONcn page; geometry not independently validated | GeoJSONcn Chaonan page lists 11 expected units and claims about 23,378 vertices / 11 polygon features, WGS84. Actual file retrieval is blocked in this execution environment; site pages conflict on whether export is free or paid. See docs/FREE_TOWNSHIP_BOUNDARY_RESEARCH.md. |
| OSM-01 | Guangdong OSM extract | Candidate identified; not downloaded/inspected | Geofabrik provides a free regional extract; inspect whether it contains all 11 suitable town-level relations. |
| GHSL-01 | GHSL built-up product | Candidate identified | Select exact product/epoch; test download and inspect coverage and metadata |
| GHSL-02 | GHSL built surface product | Candidate identified | Verify product metadata, resolution, year and access |
| WC-01 | ESA WorldCover | Candidate identified | Test download and use as a cross-check if appropriate |
| DATA-01 | Data manifest | Partially updated | District file checked; township geometry still needs actual acquisition and QA |
| QA-01 | Reusable validation script | Pending | Add after source formats and required libraries are confirmed |

## Immediate next actions

1. Obtain the GeoJSONcn export only if the page's actual export flow allows it without payment, or ask the user to download/upload the file if it is available to them.
2. Validate the actual vector file: feature count, 11 expected names/codes, geometry types and validity, CRS, extents, gaps/overlaps, and fit inside the Chaonan district boundary.
3. Check displayed terms and provenance before using the geometries in a public research output.
4. Query OSM/Overpass for all 11 names and inspect actual relations as an alternative open-licence route.
5. Select and validate one built-up dataset. Do not begin final area calculations or map production until administrative and built-up data pass QA.
