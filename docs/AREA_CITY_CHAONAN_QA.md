# AreaCity Chaonan District Boundary — QA Record

**Check date:** 2026-10-25  
**Source archive:** `ok_geo.csv.7z`, AreaCity-JsSpider-StatsGov release `2025.251231.260403`  
**Official source page:** https://xiangyuecn.github.io/AreaCity-JsSpider-StatsGov/assets/download.html

## Acquisition and extraction

- The user supplied the archive in this conversation.
- Archive size: 16,518,032 bytes.
- Archive SHA-256: `675c3e9b8dec6444994d3ef53259a145304f6a957db8a5e601e55c0b9e61e21a`.
- Extracted `ok_geo.csv`: 166,898,134 bytes.
- Parsed records: 3,635.
- Columns: `id,pid,deep,name,ext_path,geo,polygon`.
- Target record found: `id=440514`, `pid=4405`, `deep=2`, `name=潮南区`, `ext_path=广东省 汕头市 潮南区`.

## Geometry checks

- Source coordinate system: GCJ-02 according to source documentation; it is not WGS84.
- Geometry encoding: comma-separated longitude/latitude pairs in the `polygon` field.
- Coordinate pairs: 788.
- Approximate coordinate bounds: longitude 116.244570–116.621219, latitude 23.039823–23.302862.
- Parsed geometry type: Polygon.
- Shapely validity: passed (`Valid Geometry`).
- Source coordinate ring is not explicitly closed; the geometry parser implicitly closes it.
- The record encodes one exterior ring and does not encode interior rings/holes.

## Area caution

A rough diagnostic calculation using the WGS84 ellipsoid directly on the unconverted GCJ-02 coordinates gives approximately **624.147 km²**. This is **not accepted as the final district area**: the coordinates have not been converted to a suitable analysis datum/CRS, and the source geometry has not yet been cross-checked against an authoritative boundary. Do not cite this diagnostic as an official area.

## Assessment

**Status: downloaded and extracted; target record located; basic geometry validity passed; final suitability pending.**

This archive only contains province/city/district-level geometry. It does not provide the 11 township/street polygons required for the full project. Review data-specific licence terms and coordinate conversion before redistribution or final area calculation.
