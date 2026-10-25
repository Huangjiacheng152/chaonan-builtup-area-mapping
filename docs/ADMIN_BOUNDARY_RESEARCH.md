# Administrative Boundary Source Research

**Research date:** 2026-10-25  
**Phase:** 1 — Data feasibility validation  
**Status:** Preliminary source review only; no boundary file has yet been downloaded or validated.

## Research question

Can an ordinary user obtain usable boundary polygons for:
1. Chaonan District, Shantou, Guangdong (潮南区); and
2. all 11 town-level divisions in the district?

The intended use is GIS overlay and town-level area summaries, so a name list or a map screenshot alone is not sufficient. We need actual spatial geometries, a usable coordinate reference system, clear provenance, and terms that permit the intended use.

## Candidate sources and findings

### ADMIN-CANDIDATE-01 — AreaCity-JsSpider-StatsGov (GitHub)

Source: https://github.com/xiangyuecn/AreaCity-JsSpider-StatsGov

Observed from the public README:
- The repository is public and its code repository indicates an MIT licence.
- The project documents free administrative-level CSV files for province/city/district/town names and hierarchy.
- Its downloadable boundary geometry file `ok_geo.csv.7z` is for province/city/district levels (three levels), not town-level polygons.
- The README identifies the fourth-level township geometry file `ok_geo4_*.csv` as paid/ad-supported and closed-source data.
- The documented boundary coordinates in `ok_geo.csv` use GCJ-02, not WGS84.

Preliminary assessment:
- **Potentially useful for administrative-name and hierarchy cross-checks:** yes.
- **Free source of all 11 township boundary polygons:** not established; the README says township geometry is paid.
- **Free district polygon:** potentially obtainable from the three-level geometry dataset, but the actual download, extraction, coordinate handling, terms for the data, and geometry must still be checked.
- Do not assume the code repository's MIT licence automatically applies to all bundled/downloaded third-party geographic data.

### ADMIN-CANDIDATE-02 — National Earth System Science Data Center: China 1:5,000,000 township boundary (2020)

Source: https://www.geodata.cn/data/datadetails.html?dataguid=26681012531842&docId=3988

Observed from the public data page:
- It describes a national township-boundary vector dataset dated 2020, produced by digitising and checking administrative boundaries.
- Full data access requires placing an order and waiting for manual review.
- The page states research-use restrictions and says redistribution/modification/copying is not permitted without written permission.

Preliminary assessment:
- **Potential fallback only if access and terms are approved:** yes.
- **Direct, unrestricted, no-review download by an ordinary user:** no, based on the published access workflow.
- **Suitable for redistribution in this public GitHub repository:** not established and likely not without written permission.
- The 1:5,000,000 scale is also relatively coarse for detailed town-level area calculations. It may be useful for small-scale overview mapping but needs precision assessment before any use in this project.

### ADMIN-CANDIDATE-03 — GISData.cn town/street boundary package

Source: https://gisdata.cn/data-town

Observed from the public page:
- It advertises province-level township/street boundary packages in GeoJSON, with two versions.
- The page states a price of ¥19.99 per province.
- It advertises WGS84 coordinates and township names/codes.

Preliminary assessment:
- **Technically promising candidate:** perhaps.
- **Meets the project's free/open-data preference:** no, it is paid.
- Do not purchase unless the free-source route fails and the user explicitly approves a paid alternative.

### ADMIN-CANDIDATE-04 — POI86 Chaonan page

Source: https://www.poi86.com/poi/amap/district/440514/8.html

Observed from search result:
- The page lists a Chaonan District boundary and lists the expected 11 town-level names in its town-level POI section.
- It advertises boundary and other feature downloads in GeoJSON/Shapefile.

Preliminary assessment:
- The search result establishes that a page exists, not that the boundary file is freely downloadable.
- Direct page access did not complete during this research attempt.
- **Download availability, licence, geometry quality and CRS remain unverified.**
- Treat as a lead, not as a confirmed data source.

### ADMIN-CANDIDATE-05 — Official administrative information

Source: https://www.shantou.gov.cn/cnst/yxst/gk/xzqh/

The Shantou municipal government page provides administrative-division background, but the page reviewed does not establish a downloadable town-level GIS polygon dataset. Use official sources to verify names and administrative relationships; do not treat an administrative text page as a boundary file.

## Working list of 11 town-level units to verify

- 峡山街道
- 井都镇
- 陇田镇
- 成田镇
- 胪岗镇
- 两英镇
- 司马浦镇
- 陈店镇
- 仙城镇
- 红场镇
- 雷岭镇

Names and current status must be checked against a reliable administrative reference and against the actual spatial file. A POI count or town-name list is not proof that all 11 polygons are present.

## Decision so far

**No candidate has yet passed the download-and-validation gate.** The strongest openly accessible lead for free administrative names/hierarchy is AreaCity's public repository, but its township boundary geometry is explicitly listed as paid. The national geodata-centre dataset is a documented research dataset but requires manual approval and has restrictive terms. GISData.cn is paid. POI86 is unresolved.

Therefore, do not yet designate any candidate as the project's accepted boundary dataset, and do not begin town-level area calculations.

## Next checks

1. Test whether the AreaCity three-level boundary archive can be downloaded and extracted; if so, isolate the Chaonan District geometry and record its CRS and licence/terms.
2. Investigate genuinely free township polygon sources, including whether OSM actually contains complete administrative boundary relations for all 11 units. Do not assume coverage from the existence of OSM building/road data.
3. Recheck POI86's download action and terms without treating its search snippet as evidence of free access.
4. Compare any candidate township polygons with the 11-name checklist, inspect spatial coverage and geometry validity, and document source year and coordinate system.
5. If no freely downloadable complete township polygon dataset is found, report the limitation clearly and ask before considering paid or approval-based alternatives.

## Evidence-status rule

- **Discovered:** page/repository identified.
- **Downloaded:** actual file retrieved.
- **Validated:** file opens and its metadata, geometry, coverage and CRS have been checked.
- **Suitable:** evidence supports use for the intended scale and area calculations.

A source page or a successful HTTP response does not by itself mean the data are downloaded, validated, or suitable.
