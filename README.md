# Chaonan Built-up Area Mapping

**Project area:** Chaonan District (潮南区), Shantou, Guangdong, China  
**Purpose:** Use accessible open data to identify and map contiguous built-up areas across Chaonan's town-level divisions, and estimate their areas with transparent, reproducible methods.

## Current phase: Phase 1 — Data feasibility validation

Do not begin final spatial analysis or map production until the required source data have been downloaded and checked.

### Questions to resolve first
1. Can we obtain a usable boundary for Chaonan District?
2. Can we obtain boundaries for all 11 town-level divisions?
3. Can we download at least one suitable, documented built-up-area dataset covering Chaonan?
4. Can the source dates, spatial resolution, licence, completeness, and limitations be documented?

### Town-level divisions to verify
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

The list is a project checklist and must be verified against a reliable administrative source before analysis.

## Evidence status vocabulary

- **Discovered:** a candidate source or download page has been identified.
- **Downloaded:** the file has actually been retrieved.
- **Validated:** file opens and its format, coverage, coordinate reference system, attributes, and integrity have been checked.
- **Suitable:** validation shows it is fit for a specific project purpose.

A URL is not proof that a dataset has been downloaded or is suitable.

## Candidate data sources (not yet validated)

| ID | Purpose | Candidate source | Initial role |
|---|---|---|---|
| ADMIN-01 | Chaonan District boundary | To be researched | Study-area boundary |
| ADMIN-02 | 11 town-level boundaries | To be researched | Town-level summaries; critical dependency |
| OSM-01 | Buildings, roads and other mapped features | [Geofabrik Guangdong extract](https://download.geofabrik.de/asia/china/guangdong.html) | Detailed feature reference; OSM completeness varies |
| GHSL-01 | Built-up environment / built-up surface | [GHSL Data Portal](https://human-settlement.emergency.copernicus.eu/downloadWizard.php) | Candidate regional built-up dataset; select product and epoch carefully |
| GHSL-02 | Built surface area | [GHSL-BUILT-S on AWS](https://registry.opendata.aws/ghs-built-s/) | Candidate raster source; verify product, year, resolution and access |
| WC-01 | Land-cover cross-check | [ESA WorldCover data access](https://esa-worldcover.org/en/data-access) | Independent built-up / vegetation / water context; not parcel-level ground truth |

All candidates require real download and validation. Their presence in this table does not imply they are already downloaded, current, complete, or suitable.

## Repository layout

- `data/manifests/` — source register, file inventory, checksums, licences and validation status.
- `data/raw/` — optional small raw files; large source data may remain outside Git.
- `data/interim/` — intermediate data, if needed.
- `data/processed/` — derived data, with reproducible processing steps.
- `scripts/download/` — download helpers.
- `scripts/validation/` — file and spatial QA checks.
- `scripts/analysis/` — analysis scripts, after feasibility gate passes.
- `scripts/mapping/` — map production scripts, after feasibility gate passes.
- `tests/` — repeatable checks.
- `results/` — tables and summaries.
- `maps/` — map exports.
- `docs/` — methodology, decisions and evidence notes.

Empty folders may not appear in Git until a file is added.

## Data and repository policy

Do not upload large rasters, restricted data, or third-party files without checking their licence and repository limits. Prefer keeping a source manifest, download instructions, checksums, processing code and small examples in Git; store large files locally or in an appropriate external location when needed.

## Area definition

“Built-up area” can mean different things: building footprints, built-surface pixels, or the outer envelope of a contiguous built-up settlement. These are not interchangeable. The operational definition and patch-merging rules must be written down before calculating areas.

Area calculations must use a suitable projected/equal-area coordinate reference system or a defensible geodesic method, not raw longitude/latitude degree units.

## Reproducibility

Record source URL, provider, product/version, observation year, download date, licence, file name, file size, checksum, validation result, coordinate reference system, and known limitations. Keep raw data separate from derived data and document each transformation.

## Project status

See [PROJECT_STATUS.md](PROJECT_STATUS.md), [PROJECT_PLAN.md](PROJECT_PLAN.md), and [DATA_POLICY.md](DATA_POLICY.md).
