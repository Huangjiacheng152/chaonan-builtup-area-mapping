# Free Township Boundary Research — Chaonan District

**Research date:** 2026-10-25  
**Scope:** Check free public routes for the 11 town/street polygons in Chaonan District, Shantou, Guangdong.  
**Important distinction:** A website advertising data is not proof that the specific polygons are downloadable, complete, valid, or licensed for redistribution. Those checks require actual file acquisition and geometry inspection.

## Findings at a glance

| Source | Public/free signal | CRS/provenance signal | What is confirmed now | Status |
|---|---|---|---|---|
| OpenStreetMap (OSM) | OSM data and Geofabrik regional extracts are publicly available | ODbL; attribution and share-alike obligations may apply. Geometry must be assembled from relations and validated. | Shantou's OSM wiki lists Chaonan District relation 3283303. It does not confirm the 11 town-level relations. | Free candidate; town-level completeness not confirmed |
| GeoJSONcn | Website states free downloads of GeoJSON/SHP/KML/CSV etc. | Website states WGS84/EPSG:4326 and says data are collected from public sources, for learning/reference; not an official authoritative base map. Exact licence terms are not clearly stated in the page reviewed. | Site advertises nationwide township/street boundary coverage and offers an interactive regional selection/download flow. Actual Chaonan availability and file download have not been tested. | Highest-priority free candidate to test |
| AreaCity fourth-level geometry | Project page labels ok_geo4_*.csv paid/ad-supported/closed-source, with only some free test data | AreaCity repo code has MIT licence, but this should not be assumed to license paid or third-party geometry data. | It is not an established free source for all 11 town polygons. | Do not use as a free complete source unless terms/access change |
| GISData.cn | Province-level town/street package is advertised at ¥19.99 per province | WGS84 and two versions advertised | Not free under the current published price. | Exclude from free-only route unless the user later authorizes purchase |
| National Earth System Science Data Center | Dataset page describes 2020 national township boundary vector data, but access requires order/manual review | Published restrictions include limits on redistribution; scale described as 1:5,000,000 | No unrestricted direct download confirmed. | Restricted fallback, not first choice |
| GitHub lqb-zh/geojson-chinadata | Public repository, repository licence shown as MIT | README says some township data were manually exported from BIGEMAP; not a consistent authoritative source | Repository's own description notes county/district data source does not include townships; no complete Chaonan 11-unit coverage confirmed. | Low-confidence lead only |
| GitHub thedavidweng/china-village-boundaries | Public repository and CC0 dedication by uploader | README explicitly says original source is unclear, mostly circa 2016, and boundary accuracy/completeness are not officially verified | Village-level data might be dissolved into towns only if reliable parent-code mapping and coverage are independently confirmed; current evidence is insufficient. | Not suitable as a primary boundary source without substantial validation |

## OSM: what is known and what remains unknown

The OpenStreetMap Wiki page for Shantou lists Chaonan District (administrative code 440514) as relation 3283303. This is evidence of the district-level relation only. It is not evidence that all 11 town/street boundaries exist in OSM, nor that their relations use a consistent admin_level.

Sources:
- Shantou OSM Wiki: https://wiki.openstreetmap.org/wiki/Shantou
- Guangdong regional extract: https://download.geofabrik.de/asia/china/guangdong.html
- Overpass Turbo: https://overpass-turbo.eu/
- OSM copyright/licence: https://www.openstreetmap.org/copyright

Use the Overpass query documented in docs/OSM_BOUNDARY_CHECK.md to search the 11 Chinese names. Any result must be checked for relation ID, boundary=administrative, name/name:zh, admin_level, complete polygon/multipolygon geometry, plausible spatial extent and membership in Chaonan. If exact-name search returns no results, retry without suffixes and inspect the larger Guangdong extract; an empty exact-name query does not prove the boundary is absent.

OSM is a useful free route, but it has not yet passed the completeness test for the 11 units.

## GeoJSONcn: strongest free candidate to test next

The site states that it offers free nationwide administrative boundary vector data, including township/street units; it advertises GeoJSON/SHP/KML and WGS84 (EPSG:4326). Its own description says data are collected from public channels and are not an official authoritative base map, and recommends cross-checking before formal use. The page reviewed does not provide a sufficiently clear data licence for us to assume unrestricted republication of downloaded geometries.

Source: https://geojsoncn.com/

Next validation procedure:
1. Navigate Guangdong → Shantou → Chaonan District.
2. Inspect the displayed list of subordinate units and compare it against the project's 11-unit list.
3. Attempt to export a vector file (prefer GeoJSON or SHP) at no cost.
4. Preserve the original download and record access date, file hash, page/version notes and any displayed terms.
5. Inspect feature count, names/codes, geometry type, CRS, validity, extent, duplicate names, gaps and overlaps.
6. Cross-check that all 11 features belong to Chaonan and match the agreed administrative list.
7. Until terms are clear, treat it as usable for internal evaluation only; do not publish or redistribute the raw boundary file.

## Recommended decision order

1. Test GeoJSONcn first because the page explicitly advertises free town/street downloads and WGS84.
2. Test OSM in parallel using Overpass and/or a Geofabrik Guangdong extract; this route has a clearer open-data licence but may not have complete township coverage.
3. Compare both candidate boundary sets against the 11-unit list and the already checked Chaonan district polygon. Do not silently patch gaps or invent boundaries.
4. If neither passes, consider a permission-based dataset or paid source only after discussing that change in scope.
5. Proceed to final area analysis only after the administrative boundaries and built-up data both pass QA.

## Current conclusion

No complete, free, licence-clear set of all 11 Chaonan town/street polygons has been verified yet. GeoJSONcn is the best next candidate to test; OSM remains a promising alternative, but only the district-level relation has been confirmed from the reviewed public evidence.
