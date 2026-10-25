# AreaCity District Boundary Download Test

**Target file:** `ok_geo.csv.7z`  
**Source page:** https://xiangyuecn.github.io/AreaCity-JsSpider-StatsGov/assets/download.html  
**Candidate release:** 2025.251231.260403 (page states updated 2026-04-03)  
**Expected archive size:** approximately 13 MB; extracted CSV reportedly 130 MB+  
**Status:** Source confirmed as a free public download on the project page; the archive has **not** been downloaded or opened in this environment.

## Why it is worth testing

The project documents `ok_geo.csv.7z` as free three-level province/city/district boundary data. It documents the separate four-level township boundary file `ok_geo4_*.csv` as paid/ad-supported. Therefore this candidate can potentially solve ADMIN-01 (district boundary), but not ADMIN-02 (all town boundaries).

## Download steps

1. Open the source page above.
2. Under the three-level boundary section, choose `ok_geo.csv.7z` (not the paid `ok_geo4_*.csv`).
3. If the main download fails, use the source page's alternative mirror or its GitHub/Gitee Releases links.
4. Save the original archive unchanged outside GitHub if the extracted file is large.
5. Record download date, actual size, SHA-256, and the final URL used.

## Validation steps

1. Confirm the file is a valid 7z archive and can be extracted.
2. Inspect the CSV encoding, delimiter, header and row count.
3. Locate the row whose name and administrative parent chain identify Guangdong → Shantou → Chaonan (administrative code commonly written as 440514; confirm against the file).
4. Parse the boundary field using the format documented by AreaCity. Do not assume it is standard GeoJSON until inspected.
5. Convert only the Chaonan feature to a small GeoJSON/GeoPackage for review.
6. Open it in QGIS and check:
   - geometry type is Polygon or MultiPolygon;
   - it is non-empty and valid, or any repair is documented;
   - it lies in the expected part of Shantou and covers the district plausibly;
   - the extent and area are plausible against independent reference data;
   - coordinate values are consistent with the documented GCJ-02 source coordinates.
7. Preserve the source geometry. If a coordinate conversion is required, save the converted result separately and document the algorithm and limitations.

## Licence/provenance caution

The GitHub repository is labelled MIT, but the boundary geometry is described as collected from Amap's open platform. Do not automatically assume the code licence grants unrestricted rights to redistribute all underlying map geometry. Review the project terms and upstream data terms before committing the extracted boundary to a public repository. It is safer initially to store the source link, version, checksum, processing script and validation notes, and keep the full raw archive outside Git.

## Acceptance criteria for ADMIN-01

Mark as validated only when the archive was actually downloaded, extracted, parsed, and the Chaonan polygon opened and passed coverage/geometry/CRS checks. Mark as suitable only after the data terms and the expected mapping scale are acceptable.
