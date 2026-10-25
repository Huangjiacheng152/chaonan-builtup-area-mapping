# Project Status

**Last updated:** 2026-10-25  
**Current phase:** Phase 2 — District-level built-up mapping  
**Overall status:** The project scope has been simplified to avoid blocking on town/street administrative polygons. The current deliverable will map built-up areas across Chaonan District as a whole, identify contiguous built-up patches, calculate patch areas, and summarize district-level results. Town-by-town statistics are explicitly deferred until reliable town boundaries become available. The AreaCity district boundary has been extracted and basic geometry validity checked; final suitability still depends on resolving source licence/provenance and GCJ-02 coordinate handling. No built-up raster has yet been downloaded and validated.

## Scope decision

- **In scope now:** Chaonan District boundary; built-up surface/extent data; district-wide built-up patches; patch area statistics; map and QA documentation.
- **Deferred:** Town/street-level area totals for the 11 units. Do not delay district-wide mapping while seeking these polygons.
- **Important limitation:** Without validated town boundaries, do not attribute patches or built-up area to individual towns. The final report must describe results as district-level only.

## Workstream status

| ID | Item | Status | Evidence / next action |
|---|---|---|---|
| ADMIN-01 | Chaonan District boundary | Downloaded and basic geometry checks passed; final suitability pending | Record ID 440514, path 广东省 汕头市 潮南区; 788 coordinate pairs; valid Polygon. Source CRS is GCJ-02. Review provenance/licence and handle coordinate datum carefully. See docs/AREA_CITY_CHAONAN_QA.md. |
| ADMIN-02 | All 11 town-level boundaries | Deferred; not a blocker | GeoJSONcn lists the 11 units but vector export appears paid/inconsistent. No actual township file was obtained or validated. Resume only if a reliable free dataset becomes available. |
| BUILT-01 | Built-up extent dataset | Next priority | Evaluate free GHSL products, prioritizing a documented high-resolution product suitable for district-level mapping. Confirm actual download, reference year, resolution, values/threshold semantics, CRS, and licence before analysis. |
| BUILT-02 | Contiguous built-up patches | Pending dataset validation | Clip to the district boundary only after coordinate/datum compatibility is resolved. Define and document threshold, connected-component rule, minimum mapping unit, and treatment of holes/islands. |
| AREA-01 | Area calculation | Pending | Calculate in an appropriate projected/equal-area CRS or geodesically; never calculate area directly from raw longitude/latitude coordinates. |
| DATA-01 | Data manifest | Needs update as sources are selected | Record actual source, access date, download status, licence, checksum, CRS, resolution and validation result. |
| QA-01 | Reusable validation script | Pending | Build after the actual raster/vector formats and processing choices are confirmed. |

## Immediate next actions

1. Select one free, documented built-up dataset and obtain the actual file or a reproducible data access route.
2. Inspect metadata and actual data values; verify coverage over Chaonan, resolution, reference year, CRS, licence and nodata handling.
3. Resolve the district-boundary source's provenance/licence and GCJ-02 coordinate treatment before clipping or comparing against WGS84 data.
4. Define a reproducible method for extracting contiguous built-up patches and calculating their areas.
5. Produce district-level map, patch table and QA summary. Do not claim town-level statistics until town boundaries are independently validated.
