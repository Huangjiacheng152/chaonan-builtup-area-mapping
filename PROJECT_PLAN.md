# Project Plan

## Phase 1 — Data feasibility validation (current)

**Goal:** establish that ordinary users can access, download, open and use the minimum required data for Chaonan District.

### Work packages
1. **ADMIN-01 — District boundary**
   - Find candidate open sources.
   - Confirm Chaonan coverage and source date.
   - Download and inspect the actual file.
   - Record licence, attributes, CRS, geometry validity and checksum.

2. **ADMIN-02 — Town-level boundaries**
   - Seek a source containing all 11 town-level divisions.
   - Verify names and completeness against a reliable reference.
   - Confirm no missing, duplicate, invalid or obviously mismatched geometries.
   - If one source cannot provide all 11 boundaries, document alternatives and whether they can be reconciled.

3. **BUILT-01 — Built-up data**
   - Test one or more candidates such as GHSL, OSM building footprints, and ESA WorldCover.
   - Confirm the exact product, epoch/year, resolution, spatial coverage, licence, file format and download process.
   - Open the downloaded data and inspect its spatial coverage over Chaonan.
   - Decide whether it measures built surface, building footprints, or a built-up settlement envelope.

4. **Reproducibility and storage**
   - Create a source manifest.
   - Record file sizes and SHA-256 checksums where feasible.
   - Keep large files out of normal Git history unless there is a clear reason and suitable storage arrangement.
   - Record exact steps needed for another person to retrieve the same data.

### Phase 1 exit criteria
Do not move to full analysis until:
- [ ] A validated Chaonan District boundary is available.
- [ ] All 11 town-level boundaries are available, or a documented defensible alternative exists.
- [ ] At least one suitable built-up dataset has been downloaded and validated.
- [ ] The meaning of “built-up area” is explicit and supported by the selected data.
- [ ] Source dates, licence, limitations, and download steps are documented.
- [ ] A repeatable validation procedure is recorded.

## Phase 2 — Data harmonisation (only after Phase 1 passes)
- Harmonise CRS and geometry validity.
- Clip or subset datasets to the study area.
- Preserve raw data unchanged.
- Record every transformation and parameter.

## Phase 3 — Built-up patch delineation and area calculation
- Define connectivity, minimum patch size and any gap/merge rules before running analysis.
- Distinguish built surface from contiguous settlement extent.
- Calculate areas in a suitable CRS or using a documented geodesic method.
- Produce town-level summaries and uncertainty notes.

## Phase 4 — QA and map production
- Check overlay alignment, boundary coverage, omissions and edge effects.
- Compare independent sources where possible.
- Create overview and town-level maps with legend, scale, north arrow, CRS, data years and source notes.
- Export reproducible outputs and document known limitations.

## Phase 5 — Review and release
- Re-run the workflow from the documented inputs.
- Check repository contains no sensitive material or unlicensed data.
- Review map labels, units, calculations and citations.
- Publish results with a clear date and limitations statement.
