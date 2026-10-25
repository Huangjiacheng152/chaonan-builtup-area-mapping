# Data Policy

## 1. Public access and licensing

A dataset is not considered usable merely because a web page mentions it. Before adoption, record:
- data provider and product name;
- official source or download page;
- exact file or product identifier;
- licence / terms of use and attribution requirements;
- source epoch or observation year;
- download date and file format;
- spatial coverage and resolution;
- known omissions, uncertainty and restrictions.

Prefer sources that an ordinary user can access without institutional credentials or paid subscriptions. If access requires registration, special permissions, payment, or a difficult manual request, record that limitation explicitly rather than treating it as freely downloadable.

## 2. Raw data and derived data

- Never silently overwrite raw source files.
- Record processing scripts and parameters for derived files.
- Keep original provider metadata when available.
- Use distinct folders for raw, intermediate and processed data.
- Do not commit data to Git unless its licence permits redistribution and the file size is appropriate.

## 3. Large files

Git is intended primarily for text, code and manageable assets, not as an unrestricted geospatial data warehouse. Before storing a large raster or vector archive, check file size, repository impact, licence and future reproducibility. Consider local storage, a documented source download, or Git LFS / external storage where appropriate. Do not assume Git LFS is unlimited or free at any scale.

## 4. Integrity and provenance

For downloaded files, record SHA-256 when practical. Do not modify a source file to make it open without documenting the conversion and retaining a clear link to the original.

## 5. Spatial quality

For every spatial dataset, inspect:
- whether it covers Chaonan District;
- coordinate reference system (CRS);
- geometry type and validity, if vector;
- raster resolution, NoData values and class meanings, if raster;
- date / epoch and temporal relevance;
- attribute fields and administrative-name consistency;
- boundary gaps, overlaps, duplicates or clipping artefacts where relevant.

## 6. Responsible interpretation

Building footprints, built-surface pixels, land-cover classes and contiguous settlement envelopes measure different things. Do not label one as another without a defensible method. Report source years and uncertainty; do not present older source data as a precise representation of the current year.
