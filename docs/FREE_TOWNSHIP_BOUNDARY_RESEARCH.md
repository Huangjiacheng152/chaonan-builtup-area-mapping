# GeoJSONcn Check — Chaonan District Town/Street Boundaries

**Research date:** 2026-10-25  
**Target:** The 11 town/street polygons in Chaonan District, Shantou, Guangdong.  
**Important:** Page claims and a list of names are not a substitute for obtaining and validating the actual vector geometry.

## Result summary

- The GeoJSONcn Shantou page links to a Chaonan District page and labels it as having 11 subordinate units.
- The Chaonan page lists exactly these 11 names: 红场镇、两英镇、成田镇、峡山街道、雷岭镇、井都镇、仙城镇、司马浦镇、陈店镇、胪岗镇、陇田镇. This matches the project's working list.
- The page claims its GeoJSON contains all 11 units as separate Polygon or multipolygon features, with about 23,378 coordinate vertices, WGS84/EPSG:4326, and an overall area figure around 597.0 km². These are vendor/site claims, not independently verified measurements.
- **The actual GeoJSON/SHP file was not retrieved into the execution environment.** A direct HTTP request from the current environment failed because DNS resolution for geojsoncn.com is unavailable. Consequently no feature count, coordinate arrays, topology, geometry validity, or overlap/gap checks have been performed on the actual file.
- The website has inconsistent access statements: the homepage and Chaonan page use language implying free downloads, while the About page explicitly says online preview is free and vector/image downloads are paid. Do not claim a free file download has succeeded; the download flow must be checked in a normal browser.
- The site's stated provenance is public-source compilation and cleaning, not an official authoritative boundary dataset. Its About page says purchased data can be used commercially with source attribution, but project-specific usage and republication terms should be checked in the actual export/checkout terms before publication.

## Pages reviewed

- Homepage: https://geojsoncn.com/
- About/access terms: https://geojsoncn.com/about.html
- Shantou page: https://geojsoncn.com/%E5%B8%82/%E6%B1%95%E5%A4%B4%E5%B8%82.html
- Chaonan page: https://geojsoncn.com/%E5%8C%BA%E5%8E%BF/%E6%B1%95%E5%A4%B4%E5%B8%82-%E6%BD%AE%E5%8D%97%E5%8C%BA.html

## Expected list to verify against the file

1. 峡山街道
2. 井都镇
3. 陇田镇
4. 成田镇
5. 胪岗镇
6. 两英镇
7. 司马浦镇
8. 陈店镇
9. 仙城镇
10. 红场镇
11. 雷岭镇

## QA required after actual file acquisition

1. Record original file name, retrieval date, file hash, and the page/terms under which it was downloaded.
2. Parse GeoJSON or SHP and verify exactly 11 relevant features, each with the expected name and ideally administrative code.
3. Confirm geometry types are Polygon/MultiPolygon and every geometry is valid; record empty, duplicate, or null features.
4. Verify CRS metadata. The site advertises WGS84/EPSG:4326; inspect the actual GeoJSON coordinates or SHP .prj rather than assuming.
5. Check the bounds and that all 11 features are located within/near the Chaonan District boundary.
6. Compare union of the 11 units against the district polygon; quantify gaps, overlaps, outside slivers, and area mismatch. Avoid treating the site's reported 597.0 km² as authoritative.
7. Inspect licence and attribution terms; retain a copy/screenshot of the terms for project provenance.

## Conclusion

GeoJSONcn is a promising candidate because its Chaonan page explicitly lists all 11 expected units and claims polygon geometry in WGS84. However, the two essential gates—actual vector-file acquisition and independent geometry QA—remain incomplete, and the free-versus-paid download status is inconsistent across its pages. It must remain a **candidate, not a validated source**, until the actual file is obtained and inspected.

## Alternative

Continue checking OpenStreetMap relations in parallel. OSM has a clearer open-data licence (ODbL with attribution and applicable share-alike obligations), but the existence and completeness of all 11 town-level relations still require actual relation inspection.
