# OpenStreetMap Administrative Boundary Check

**Research date:** 2026-10-25  
**Status:** Candidate investigation; complete town-level polygons are not yet confirmed.

## Evidence found

The OpenStreetMap Wiki page for Shantou lists Chaonan District as relation **3283303** and district code 440514. This is evidence that an OSM relation exists for Chaonan District, but it does not establish that the 11 town-level administrative boundary relations exist or are complete.

Sources:
- https://wiki.openstreetmap.org/wiki/Shantou
- https://download.geofabrik.de/asia/china/guangdong.html

Geofabrik provides a freely downloadable Guangdong extract in OSM PBF and GeoPackage/Shapefile formats. Its current page lists the GeoPackage ZIP at approximately 326 MB. This is a regional extract, not a ready-made Chaonan town-boundary file. It must be inspected after download.

## Recommended verification method

### A. Inspect relation 3283303

Open the relation on OpenStreetMap and confirm its tags, boundary geometry, relation members, and spatial extent. Do not rely on a screenshot alone; retain the relation ID and access date.

### B. Search Overpass Turbo for town-level boundary relations

Open https://overpass-turbo.eu/ and run the following query. It searches for administrative boundary relations by exact names within the Chaonan bounding box; a returned relation is only a candidate until its geometry and tags are inspected.

```overpass
[out:json][timeout:90];
(
  relation["boundary"="administrative"]["name"="峡山街道"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="井都镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="陇田镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="成田镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="胪岗镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="两英镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="司马浦镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="陈店镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="仙城镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="红场镇"](23.05,116.25,23.45,116.65);
  relation["boundary"="administrative"]["name"="雷岭镇"](23.05,116.25,23.45,116.65);
);
out tags geom;
```

The bounding box is a broad search window, not a substitute for checking each returned geometry. If no results are returned, repeat with Chinese names without suffixes, English/transliterated names, or inspect the broader Guangdong extract. Some OSM boundaries may use different naming conventions or admin levels.

### C. Validate each candidate relation

For every returned relation, record:
- OSM relation ID and URL;
- exact `boundary`, `admin_level`, `name`, `name:zh`, `name:en`, and `type` tags where present;
- whether its geometry is a complete closed polygon/multipolygon;
- whether it lies inside Chaonan and has plausible coverage;
- whether all 11 units are present with no obvious duplicates;
- access date and licence attribution.

OpenStreetMap data are available under the Open Database Licence (ODbL); use requires attribution and may create share-alike obligations for derivative databases. Review the current OSM copyright page before distributing derived boundary data: https://www.openstreetmap.org/copyright

## Current conclusion

OSM is a promising free candidate for testing because a Chaonan District relation is documented and a Guangdong regional extract is publicly downloadable. **No evidence yet confirms all 11 town-level polygon relations are present and complete.** Do not mark ADMIN-02 validated until the actual geometry has been inspected.
