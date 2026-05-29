# Madagascar Administrative Divisions / Madagasikara



## Overview

| Item | Details |
|------|---------|
| Region | 22 |
| District | 119 |
| Commune | 1,579 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-29 |
| Website | [openadmindata.org/mg](https://openadmindata.org/mg/) |
| API | [openadmindata.org/api/mg](https://openadmindata.org/api/mg/) |

## Browse by Region

| # | Region | Districts | Communes | Link |
|---|----|----|----|------|
| 1 | Analamanga | 13 | 139 | [Browse](divisions/analamanga/) |
| 2 | Vakinankaratra | 7 | 91 | [Browse](divisions/vakinankaratra/) |
| 3 | Itasy | 3 | 51 | [Browse](divisions/itasy/) |
| 4 | Bongolava | 2 | 26 | [Browse](divisions/bongolava/) |
| 5 | Haute Matsiatra | 7 | 88 | [Browse](divisions/haute-matsiatra/) |
| 6 | Amoron I Mania | 4 | 55 | [Browse](divisions/amoron-i-mania/) |
| 7 | Vatovavy Fitovinany | 6 | 139 | [Browse](divisions/vatovavy-fitovinany/) |
| 8 | Ihorombe | 3 | 26 | [Browse](divisions/ihorombe/) |
| 9 | Atsimo Atsinanana | 5 | 90 | [Browse](divisions/atsimo-atsinanana/) |
| 10 | Atsinanana | 7 | 88 | [Browse](divisions/atsinanana/) |
| 11 | Analanjirofo | 6 | 63 | [Browse](divisions/analanjirofo/) |
| 12 | Alaotra Mangoro | 5 | 79 | [Browse](divisions/alaotra-mangoro/) |
| 13 | Boeny | 6 | 44 | [Browse](divisions/boeny/) |
| 14 | Sofia | 7 | 108 | [Browse](divisions/sofia/) |
| 15 | Betsiboka | 3 | 35 | [Browse](divisions/betsiboka/) |
| 16 | Melaky | 5 | 37 | [Browse](divisions/melaky/) |
| 17 | Atsimo Andrefana | 9 | 110 | [Browse](divisions/atsimo-andrefana/) |
| 18 | Androy | 4 | 51 | [Browse](divisions/androy/) |
| 19 | Anosy | 3 | 64 | [Browse](divisions/anosy/) |
| 20 | Menabe | 5 | 51 | [Browse](divisions/menabe/) |
| 21 | Diana | 5 | 65 | [Browse](divisions/diana/) |
| 22 | Sava | 4 | 79 | [Browse](divisions/sava/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 22 region records |
| [all-district.json](data/all-district.json) | JSON | All 119 district records |
| [all-commune.json](data/all-commune.json) | JSON | All 1,579 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=district, 3=commune |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{district-slug}/
```

Communes are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Madagascar Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/madagascar-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
