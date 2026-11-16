# Awesome South Tyrol Data [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of open data sources, APIs and tools for South Tyrol (Südtirol / Alto Adige), Italy.
>
> Offene Daten, Schnittstellen und Werkzeuge für Südtirol · Dati aperti, API e strumenti per l'Alto Adige

Only sources that are publicly reachable and free to use are listed. Each entry says how machine-readable it is:

- **Access:** `API` (documented interface), `Download` (files), `OGC` (WMS/WFS map services) or `Web` (website only)
- **Format:** for example JSON, CSV, XLSX, GTFS
- **Licence:** as stated by the source. Where it differs per dataset or record, the entry says so. Check before you reuse data.
- **Key:** `no key` means you can read the data without registering.

Missing a source? Open an issue or a pull request. All links are checked automatically once a month.

## Contents

- [Quick start](#quick-start)
- [Data portals](#data-portals)
- [Tourism and accommodation](#tourism-and-accommodation)
- [Mobility](#mobility)
- [Maps and geodata](#maps-and-geodata)
- [Weather, avalanches and environment](#weather-avalanches-and-environment)
- [Statistics and municipalities](#statistics-and-municipalities)
- [Health](#health)
- [Law and administration](#law-and-administration)
- [Language resources](#language-resources)
- [Calendars and holidays](#calendars-and-holidays)
- [Code from public bodies](#code-from-public-bodies)
- [Projects built on this data](#projects-built-on-this-data)

## Quick start

Three calls that return data right away, no key needed:

```sh
# Datasets in the provincial open data portal (CKAN)
curl 'https://data.civis.bz.it/api/3/action/package_search?q=comuni&rows=5'

# Accommodation from the Open Data Hub, fields in German, Italian and English
curl 'https://tourism.api.opendatahub.com/v1/Accommodation?pagesize=5'

# Public transport timetables of STA as a GTFS zip file
curl -o sta-gtfs.zip 'https://gtfs.api.opendatahub.com/v1/dataset/sta-time-tables/raw'
```

## Data portals

- [Open Data Hub](https://opendatahub.com) – Regional open data platform run by NOI Techpark for tourism, mobility and more. [Docs](https://docs.opendatahub.com) · [Data Browser](https://databrowser.opendatahub.com) · [Source code](https://github.com/noi-techpark)
  `API` · JSON · licence per record · `no key` for most data, anonymous access is rate-limited · OpenAPI/Swagger docs, CLI and R package
- [Open Data Portal South Tyrol](https://data.civis.bz.it) – CKAN catalogue of the Autonomous Province of Bozen/Bolzano, about 930 datasets, with the standard [CKAN API](https://data.civis.bz.it/api/3/action/package_search). Also reachable as dati.retecivica.bz.it.
  `API` `Download` `OGC` · WMS/WFS, PDF, CSV, XLS, JSON · licence per dataset, about 9 in 10 under CC0 · `no key` · full-text search finds Italian terms (`acqua`), German ones often return nothing

## Tourism and accommodation

- [Open Data Hub Tourism API](https://tourism.api.opendatahub.com/v1) – Accommodation, points of interest, events and activities.
  `API` · JSON · licence per record: entries from LTS (the South Tyrolean tourism association) under CC0, other sources under CC BY or CC BY-SA · `no key` · texts in German, Italian, English and more

## Mobility

- [Open Data Hub GTFS API](https://gtfs.api.opendatahub.com) – Public transport timetables of STA (bus, train, cable cars) in the GTFS standard, with realtime feeds (GTFS-RT). Also SkyAlps flights and carpooling trips.
  `API` `Download` · GTFS, GTFS-RT, JSON · CC0 · `no key`
- [Open Data Hub Mobility API](https://mobility.api.opendatahub.com) – Time series for parking, e-charging, traffic, bike sharing and more.
  `API` · JSON · licence per data origin · `no key`
- [südtirolmobil](https://www.suedtirolmobil.info) – Journey planner and public transport information for travellers.
  `Web`

## Maps and geodata

- [Geoportal South Tyrol](https://geoportale.retecivica.bz.it) – Official geodata of the province. The map services are listed in the [Open Data Portal](https://data.civis.bz.it).
  `OGC` · WMS, WFS, WCS · licence per dataset, mostly CC0
- [MapView GeoBrowser](https://mapview.civis.bz.it) – Map viewer with the GeoCatalogue, combine layers and export maps.
  `Web`
- [OpenStreetMap: Alto Adige](https://wiki.openstreetmap.org/wiki/Alto_Adige) – Community page for mapping South Tyrol, with local conventions and import notes.
  `Web` · OpenStreetMap data under ODbL

## Weather, avalanches and environment

- [Wetter Südtirol](https://wetter.provinz.bz.it) – Official weather service of the province.
  `Web`
- [Civil protection datasets](https://data.civis.bz.it/organization/southtyrolean-civil-protection-agency) – 15 datasets of the Agency for Civil Protection in the Open Data Portal.
  `Download` · JSON, XML, XLSX, PDF · CC0 or CC BY per dataset · `no key`
- [Nature and landscape datasets](https://data.civis.bz.it/organization/pab-natura-paesaggio-e-sviluppo-del-territorio) – 47 datasets of the provincial department for nature, landscape and spatial development, mostly map layers.
  `OGC` · WMS, WFS, GeoTIFF · mostly CC0 · `no key`
- [Avalanche report Euregio](https://avalanche.report) – Daily avalanche bulletin for Tyrol, South Tyrol and Trentino. The latest bulletin is also published as [JSON in the CAAML v6 standard](https://avalanche.report/bulletins/latest/EUREGIO_en_CAAMLv6.json) (replace `en` with `de` or `it`).
  `Web` `API` · JSON (CAAML v6) · `no key`
- [Eurac Environmental Data Platform](https://edp-portal.eurac.edu) – Environmental and climate research data from Eurac Research.
  `Download` · licence per dataset

## Statistics and municipalities

- [ASTAT](https://astat.provinz.bz.it) – Provincial statistics institute: population, economy, tourism. Some tables are also in the Open Data Portal.
  `Web` `Download`
- [ISTAT municipality codes](https://www.istat.it/classificazione/codici-dei-comuni-delle-province-e-delle-regioni/) – Official codes for all Italian municipalities, including the 116 in South Tyrol.
  `Download` · XLSX · CC BY 4.0 · `no key`

## Health

- [Provincial health department datasets](https://data.civis.bz.it/organization/provincia-autonoma-di-bolzano-alto-adige-sanita) – 55 datasets of the provincial health department in the Open Data Portal.
  `Download` · CSV, PDF · CC0 · `no key`
- [South Tyrolean Health Service datasets](https://data.civis.bz.it/organization/southtyrolean-health-agency) – 6 datasets of the South Tyrolean Health Service.
  `Download` · JSON, CSV, XLS, XML · mostly CC0 · `no key`

## Law and administration

- [LexBrowser](https://lexbrowser.provinz.bz.it) – Provincial laws and regulations.
  `Web`
- [Public procurement datasets](https://data.civis.bz.it/organization/southtyrolean-agency-for-public-contracts) – 23 datasets of the Agency for Public Contracts.
  `Download` · XLS, XML, ODS, PDF · CC0 · `no key`

## Language resources

- [bistro](https://bistro.eurac.edu) – Eurac Research terminology system for legal and administrative language in German and Italian.
  `Web`
- [Istitut Ladin Micurà de Rü](https://www.micura.it/en/) – Institute for the Ladin language, the third official language in parts of South Tyrol. Online [dictionaries](https://www.micura.it/la/dizionars), grammar and a [spell checker](https://www.micura.it/la/sorvisc-online/coretur-ortografich).
  `Web`

Place names in South Tyrol are a sensitive topic. This list only links to official and established sources and takes
no position on naming.

## Calendars and holidays

- [Nager.Date public holidays API](https://date.nager.at/api/v3/PublicHolidays/2026/IT) – Italian public holidays. Whit Monday is listed for the region code `IT-32`; in practice it is a holiday in South Tyrol.
  `API` · JSON · `no key`

## Code from public bodies

- [Autonomous Province of Bozen/Bolzano on GitHub](https://github.com/provbz) – Includes a bilingual (German and Italian) stylesheet for the Italian e-invoice.
- [NOI Techpark on GitHub](https://github.com/noi-techpark) – Source code of the Open Data Hub and its web components.

## Projects built on this data

- [tyrolean-map](https://github.com/simon04/tyrolean-map) – Frontend to maps published by Land Tirol and South Tyrol as open government data.
- [MonalisR](https://github.com/mattia6690/MonalisR) – R package to access environmental and meteorological data in South Tyrol.
- [South-Tyrol-Trails](https://github.com/bmattivi03/South-Tyrol-Trails) – Hiking and cycling route explorer built on the Open Data Hub.
- [Open Data Hub use cases](https://opendatahub.com/use-cases/) – Companies and projects that use Open Data Hub data.

## Contributing

Pull requests welcome. Each entry: name, link, one sentence on what it offers, then access, format, licence and key as stated
by the source. Only free, publicly reachable sources.

## Licence

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — maintained by Florian Berger ([Berger+Team](https://berger.team)), Bolzano, for [btlabs Core](https://btlabs.dev/en).
