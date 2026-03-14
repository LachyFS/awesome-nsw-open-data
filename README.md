# Awesome NSW Open Data [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of every useful open dataset, API, and data source published by the New South Wales (Australia) government - for builders, journalists, researchers, and the curious.

NSW publishes **22,000+ datasets** across dozens of portals. Most of it is underused. This list focuses on data that's actually interesting to build with: real-time APIs, granular CSVs, spatial layers, and PDF-trapped gems worth liberating.

**Why this exists:** Government data portals are hard to navigate and discoveries stay siloed. This repo is a single place to find the good stuff, with enough context to know what you can actually build.

## Contents

- [🗂 Portals & Catalogs](#-portals--catalogs)
- [🚆 Transport & Roads](#-transport--roads)
- [🏠 Property & Land](#-property--land)
- [🏥 Health](#-health)
- [🔒 Crime & Justice](#-crime--justice)
- [🌿 Environment & Climate](#-environment--climate)
- [💸 Fines & Revenue](#-fines--revenue)
- [🎰 Gambling](#-gambling)
- [🍽 Food Safety](#-food-safety)
- [🎓 Education](#-education)
- [📊 Demographics & Economics](#-demographics--economics)
- [🗺 Geospatial Foundation](#-geospatial-foundation)
- [📄 PDF-Trapped Data Worth Liberating](#-pdf-trapped-data-worth-liberating)
- [Contributing](#contributing)

---

## 🗂 Portals & Catalogs

The master indexes. Start here to search across agencies.

| Portal | Datasets | Notes |
|--------|----------|-------|
| [Data.NSW](https://data.nsw.gov.au) | ~16,857 | Main catalog. CKAN-based with API access. CSV, JSON, XLSX, spatial. |
| [SEED](https://datasets.seed.nsw.gov.au) | ~5,200 | Environment-focused. WMS, GeoTIFF, Shapefile, NetCDF. |
| [Transport Open Data Hub](https://opendata.transport.nsw.gov.au) | 230+ datasets / 1,000+ resources | Best developer experience of any NSW portal. Free API key required. |
| [API.NSW](https://api.nsw.gov.au) | 25+ APIs | Gateway for structured REST APIs (fuel prices, etc). API key required. |
| [NSW Planning Portal Open Data](https://www.planningportal.nsw.gov.au/opendata) | 63+ | Zoning, DAs, heritage, flood overlays. REST, WMS, WFS, Shapefile. |
| [Spatial Collaboration Portal](https://portal.spatial.nsw.gov.au) | ~300 layers | Foundation spatial data across 10 themes. |
| [ELVIS](https://elevation.fsdf.org.au) | - | LiDAR point clouds and DEMs. 15GB per request limit. |
| [NSW Flood Data Portal](https://flooddata.ses.nsw.gov.au) | 2,300+ | Flood studies, extent mapping, planning levels from 120+ orgs. |
| [NSW Spatial Digital Twin](https://nsw.digitaltwin.terria.io) | - | 3D/4D visualization of combined spatial datasets. |

---

## 🚆 Transport & Roads

Transport for NSW has the richest API ecosystem in Australian government: **35,700+ registered developers** and **9,000+ apps** built on it. All APIs require a [free API key](https://opendata.transport.nsw.gov.au).

### Real-Time Feeds

| Dataset | Format | Update Freq | Description |
|---------|--------|-------------|-------------|
| [Timetables Complete GTFS](https://opendata.transport.nsw.gov.au/dataset/timetables-complete-gtfs) | GTFS ZIP | Daily | Static timetables, stops, route shapes for ALL operators |
| [Realtime Vehicle Positions](https://opendata.transport.nsw.gov.au/dataset/public-transport-realtime-vehicle-positions) | GTFS-R Protobuf | **15 seconds** | GPS position of every bus, train, ferry, metro, light rail vehicle |
| [Realtime Trip Updates](https://opendata.transport.nsw.gov.au/dataset/public-transport-realtime-trip-update) | GTFS-R Protobuf | **15 seconds** | Delays, changed stopping patterns, cancellations |
| [Realtime Alerts](https://opendata.transport.nsw.gov.au/dataset/public-transport-realtime-alerts) | GTFS-R Protobuf | Real-time | Service disruptions at stop/trip/line level |
| [Historical GTFS & GTFS-R](https://opendata.transport.nsw.gov.au/data/dataset/) | GTFS | Archive | Archived timetable and realtime data for multi-year punctuality analysis |
| [Timetables TransXChange](https://opendata.transport.nsw.gov.au/dataset/timetables-complete-transxchange) | XML (TXC) | Daily | Includes **school bus routes** not yet in GTFS |

### Trip Planning APIs

Five endpoints at [`/dataset/trip-planner-apis`](https://opendata.transport.nsw.gov.au/dataset/trip-planner-apis):

- **Stop Finder** - autocomplete for stops/stations
- **Trip Planner** - full routing with Opal fare calculation
- **Departure** - real-time departure boards for any stop
- **Service Alert** - active alerts by route/stop
- **Coordinate Request** - find stops near a GPS coordinate

### Traffic & Roads

| Dataset | Format | Description |
|---------|--------|-------------|
| [Live Traffic Cameras](https://opendata.transport.nsw.gov.au/dataset/live-traffic-cameras) | GeoJSON API + images | ~60 second refresh. Great for timelapse aggregators. |
| [Live Traffic Hazards](https://opendata.transport.nsw.gov.au/dataset/live-traffic-hazards) | GeoJSON API | Real-time incidents with GPS coordinates |
| [NSW Crash Data](https://opendata.transport.nsw.gov.au/data/dataset/nsw-crash-data) | CSV | 5+ years of crash locations, conditions, injuries, fatalities |
| [Speed Zones](https://opendata.transport.nsw.gov.au/dataset/speed-zones) | Shapefile, CSV, JSON, KML | Every speed limit in NSW |
| [NSW Speed Cameras](https://opendata.transport.nsw.gov.au/dataset/nsw-speed-cameras) | CSV + XLSX | Fixed, red-light, and mobile camera locations with GPS coordinates |
| [Mobile Speed Camera Routes](https://opendata.transport.nsw.gov.au/dataset/nsw-speed-cameras) | CSV + **53-page PDF** | Approved mobile camera zones |
| [Toll Calculator API](https://opendata.transport.nsw.gov.au/dataset/toll-calculator-api) | REST API | Calculate toll costs for any trip across all Sydney motorways |
| [Historic Travel Time Data](https://opendata.transport.nsw.gov.au/dataset/historic-roads-travel-time-data-ttds) | API/Download | Historical congestion patterns for "best time to drive" analysis |
| [Speeding Fines by Camera](https://opendata.transport.nsw.gov.au/dataset/data-on-speeding-fines-issued-speeding-cameras-and-nsw-police) | Download | Which cameras generate the most fines |
| [Speeding Fines by Offender Postcode](https://opendata.transport.nsw.gov.au/dataset/data-on-speeding-fines-offender's-postcode) | Download | "Which suburb speeds the most?" |
| [NSW Clearways](https://opendata.transport.nsw.gov.au/dataset/nsw-clearways) | Dataset | Every clearway with times |
| [Traffic Lights Location](https://opendata.transport.nsw.gov.au/dataset/traffic-lights-location) | Dataset | Every traffic signal in NSW |
| [EV Charging Stations](https://opendata.transport.nsw.gov.au/dataset/electric-vehicle-charging-stations-nsw) | CSV | AC/DC chargers with plug types, power specs. Quarterly updates. |

### Opal & Patronage

| Dataset | Format | Description |
|---------|--------|-------------|
| [Opal Trips - All Modes](https://opendata.transport.nsw.gov.au/dataset/opal-trips-all-modes) | CSV/XLSX | Monthly tap-on/off data across train, metro, bus, ferry, light rail (from July 2016) |
| [Opal Patronage](https://opendata.transport.nsw.gov.au/dataset/opal-patronage) | CSV | Daily patronage by mode, day of week, commercial centre (from Jan 2020). COVID recovery tracker. |
| [Bus Occupancy (BOAM)](https://opendata.transport.nsw.gov.au) | S3/PDF | Historic bus occupancy indicator for individual services |
| [Bus On-Time Running](https://opendata.transport.nsw.gov.au) | CSV | Punctuality by contract area since 2010 |
| [Fare Compliance Survey](https://opendata.transport.nsw.gov.au) | CSV/XLSX | Fare evasion rates since 2012 by mode |
| [Household Travel Survey](https://opendata.transport.nsw.gov.au) | XLSX/CSV | How and why people in Greater Sydney travel |

### Maritime

16 datasets with CSV, GeoJSON, KML, and Shapefile: boat ramps, public moorings, wharves, coastal bars, shallow water areas, speed zones, no-wash zones, no-towing zones, restricted zones, navigation aids, and **maritime webcams**. Plus a **Maritime Alerts Reporting Platform API** for real-time safety alerts.

---

## 🏠 Property & Land

Property data has the highest viral potential of any NSW data category. Australians are property-obsessed, and the government publishes remarkably granular data.

### Sales & Valuations

| Dataset | Format | Description |
|---------|--------|-------------|
| [Valuer General Property Sales](https://valuation.property.nsw.gov.au/embed/propertySalesInformation) | Weekly ZIP of `.DAT` files (CC BY 4.0) | **Every property sale in NSW since 1990** - price, date, property details, zoning, lot area |
| [nswpropertysalesdata.com](https://nswpropertysalesdata.com) | Daily CSV | Third-party convenience wrapper for the above |
| [Bulk Land Value Information](https://data.nsw.gov.au/data/dataset/bulk-land-value-information) | Monthly CSV by LGA | Current land values for every property in NSW (5 valuing years) |

### Development Applications

| Dataset | Format | Description |
|---------|--------|-------------|
| [Online DA Data API](https://www.planningportal.nsw.gov.au/opendata/dataset/online-da-data-api) | REST API (JSON) | All DAs since Jan 2019. Mandatory for all councils since July 2021. Free subscription key required. |
| [Online CDC Data API](https://www.planningportal.nsw.gov.au/opendata/dataset/online-cdc-data-api) | REST API (JSON) | Complying Development Certificates - fast-track building approvals |
| [Planning Portal Spatial Viewer](https://www.planningportal.nsw.gov.au/spatialviewer) | Interactive web map | Zoning, heritage, flood, environmental constraints for any address |

### Zoning & Planning Controls

The [Planning Portal Open Data](https://www.planningportal.nsw.gov.au/opendata/dataset/) publishes ~63 spatial Environmental Planning Instrument (EPI) layers as Shapefile, WMS, WFS, and ArcGIS REST:

- **Land Zoning (LZN)** - every land use zone (Residential, Business, Industrial, etc.)
- **Height of Buildings (HOB)** - maximum permitted building heights
- **Floor Space Ratio (FSR)** - maximum buildable floor area
- **Minimum Lot Size (LSZ)** - subdivision controls
- **Heritage Conservation Areas**
- **Flood Prone Land, Acid Sulfate Soils, Groundwater Vulnerability, Urban Release Areas**, and dozens more

### Rental & Housing

| Dataset | Format | Description |
|---------|--------|-------------|
| [Rental Bond Data](https://www.nsw.gov.au/housing-and-construction/rental-forms-surveys-and-data/rental-bond-data) | XLSX/CSV (monthly, CKAN API) | Every bond lodgement by postcode - dwelling type, rent amount, bedrooms |
| [Housing Rent and Sales Dataset](https://www.planningportal.nsw.gov.au) | Tableau + Excel | Median weekly rent and sales prices by LGA over time |
| [Social Housing Dashboard](https://www.dcj.nsw.gov.au) | Interactive Tableau | Waiting lists, median wait times, occupancy by region |

### Land Records & Registers

| Dataset | Format | Description |
|---------|--------|-------------|
| [NSW Digital Cadastre (DCDB)](https://data.nsw.gov.au/data/dataset/spatial-services-nsw-cadastre) | WMS/WFS, ArcGIS REST, File Geodatabase | Every land parcel boundary. Daily updates. |
| [NSW Land Tenure](https://data.nsw.gov.au/data/dataset/nsw-land-tenure) | Spatial | Wall-to-wall ownership: Crown, Private, National Park, Indigenous, State Forest |
| [Strata Search](https://www.nsw.gov.au/housing-and-construction/strata/strata-search) | Web + weekly ArcGIS | Every strata scheme - plan number, agent, last AGM |
| [Contaminated Land Register](https://www.epa.nsw.gov.au/Your-environment/Contaminated-land/notified-and-regulated-contaminated-land/list-of-notified-sites) | Web DB + monthly Excel/PDF | Every notified contaminated site. Updated monthly. |
| [State Heritage Register](https://datasets.seed.nsw.gov.au/dataset/state-heritage-register-curtilages1c5ee) | Shapefile, ArcGIS REST, WMS | 1,650+ state heritage items + 30,000+ in broader inventory |
| Crown Land | SEED + Planning Portal | ArcGIS REST | All government-owned land |

---

## 🏥 Health

### HealthStats NSW

[HealthStats NSW](https://www.health.nsw.gov.au/hsnsw/Pages/default.aspx) aggregates hundreds of health indicators across topics from Aboriginal Health to Vaping. Data available by **Local Health District, LGA, and Primary Health Network**. Key indicators: smoking rates, obesity, diabetes hospitalisations, mental health ED presentations, immunisation coverage, potentially preventable hospitalisations.

### Hospital & Ambulance Performance

The [Bureau of Health Information (BHI)](https://www.bhi.nsw.gov.au) is the independent healthcare performance authority.

| Dataset | Format | Description |
|---------|--------|-------------|
| [BHI Data Portal](https://www.bhi.nsw.gov.au/BHI_reports) | Interactive dashboard + Excel/CSV | ED wait times, elective surgery waits, ambulance response times, admitted patient data for 80+ hospitals since 2010 |
| Ambulance Response Times by SA3 | Interactive map + Data Portal | Median response times for life-threatening (P1A) and urgent (P2) calls across **91 SA3 areas** |
| Seclusion & Restraint Supplement | **PDF** + data tables | Quarterly data on seclusion/restraint in 40+ mental health inpatient units by hospital |
| Patient Surveys | PDF + supplementary tables | ED, admitted, maternity patient experience - 23,000+ respondents per cycle |
| [Mental Health Reports](https://www.bhi.nsw.gov.au/topics/mental-health) | PDF + data portal | Mental health ED presentations, readmissions, seclusion rates |

### Disease Surveillance

| Dataset | Format | Description |
|---------|--------|-------------|
| [Notifiable Diseases Data](https://www.health.nsw.gov.au/Infectious/Pages/data.aspx) | Interactive dashboards | ~70 notifiable conditions including COVID, influenza, salmonella, syphilis |
| [Immunisation Coverage by LHD](https://www.health.nsw.gov.au/immunisation/Pages/coverage-by-lhd.aspx) | HTML tables | Quarterly immunisation rates by Local Health District and Aboriginality |
| [Arbovirus & Mosquito Surveillance](https://data.nsw.gov.au/insights/arbovirus) | Data portal | Mosquito trapping data from 1984, sentinel chicken seroconversion from 2003 |
| Respiratory Surveillance Reports | Fortnightly PDF | Ongoing COVID, influenza, RSV surveillance including sewage sampling |

### COVID-19 Archives

All frozen October 2023 but fully accessible:

| Dataset | URL | Format |
|---------|-----|--------|
| [Cases by Location](https://data.nsw.gov.au/data/dataset/covid-19-cases-by-location) | data.nsw.gov.au | CSV + CKAN API |
| [Cases by Age Range](https://data.nsw.gov.au/data/dataset/nsw-covid-19-cases-by-age-range) | data.nsw.gov.au | CSV + CKAN API |
| [Case Locations (exposure sites)](https://data.nsw.gov.au/data/dataset/nsw-covid-19-case-locations) | data.nsw.gov.au | CSV (discontinued Nov 2021) |
| Tests by Location | data.nsw.gov.au | CSV |
| [COVID-19 in NSW](https://www.health.nsw.gov.au/Infectious/covid-19/Pages/stats-nsw.aspx) | health.nsw.gov.au | Interactive dashboard |

### Other Health Data

| Source | URL | Notes |
|--------|-----|-------|
| Emergency Department Wait Times | emergencywait.health.nsw.gov.au | Real-time estimated waits. Could be scraped and archived for trends. |
| [Cancer Statistics NSW](https://www.cancer.nsw.gov.au/research-and-data/cancer-data-and-statistics/data-available-now/cancer-statistics-nsw) | cancer.nsw.gov.au | Incidence, mortality, survival by cancer type, sex, age, geography. Registry dates to 1972. |
| [NSW Cancer Registry](https://www.cancer.nsw.gov.au/research-and-data/cancer-data-and-statistics/data-available-on-request/request-unit-record-data-for-research/nsw-cancer-registry) | cancer.nsw.gov.au | Unit-record data available on request for research |

---

## 🔒 Crime & Justice

[BOCSAR](https://bocsar.nsw.gov.au) (Bureau of Crime Statistics and Research) publishes the most granular, longest-running crime data of any Australian state. Most data goes back to **1995**, the Reoffending Database to **1994**.

### BOCSAR Open Datasets

All downloadable as XLSX:

| Dataset | URL | Description |
|---------|-----|-------------|
| Monthly Criminal Incidents | [criminal-offences-data](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/criminal-offences-data.html) | 62 offence types by LGA/SA4, monthly since 1995 |
| Local Area Rankings | [local-area-rankings](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/local-area-rankings.html) | LGA crime rate rankings - "safest suburb" content |
| LGA Snapshots | [local-area-datasets](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/local-area-datasets.html) | One Excel per LGA: incidents, offenders, victims, demographics |
| Daily Criminal Incidents | [daily-incident-data](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/daily-incident-data.html) | Day-by-day patterns for time-of-day analysis |
| [Hotspot Maps & Spatial Data](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/hotspot-maps---data.html) | Point-level spatial data for 11 offence types |
| Custody Data | [custody-data](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/custody-data.html) | Prison population by age, sex, Aboriginal status, legal status |
| Alleged Offender Dataset | [alleged-offender-dataset](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/alleged-offender-dataset.html) | Offender demographics by offence type |
| [Crime Trend Data](https://bocsar.nsw.gov.au/statistics-dashboards/open-datasets/trend-data-files.html) | Pre-calculated 2/5/10-year trends with statistical significance |

### BOCSAR Dashboards & Tools

| Tool | Description |
|------|-------------|
| [Crime Mapping Tool](https://crimetool.bocsar.nsw.gov.au/bocsar) | Interactive maps/graphs since 1995. Filter by DV, alcohol, time of day, premises. |
| [Sentencing Tool](https://bocsar.nsw.gov.au/statistics-dashboards/court-and-sentencing/user_guide_sentencing_tool.html) | Actual sentences by offence type, penalty, gender |
| [Bail Dashboard](https://bocsar.nsw.gov.au/topic-areas/bail.html) | Bail decisions, conditions, breaches by demographics |
| [Policing Activity Dashboard](https://bocsar.nsw.gov.au/media/2024/nsw-policing-activity-dashboard.html) | **New 2024** - police searches (incl. strip searches), move-on orders, use of force |
| [Reoffending Data](https://bocsar.nsw.gov.au/topic-areas/re-offending.html) | Every person convicted since 1994. 49.3% adult recidivism within 12 months. |

### Domestic Violence & Coercive Control

BOCSAR publishes DV statistics (victim/perpetrator demographics) and [AVO/coercive control monitoring data](https://bocsar.nsw.gov.au/media/2024/new-domestic-violence-data-avo-and-coercive-control.html) as downloadable XLSX. 100,111 ADVOs in force Q2 2024 (up 52% since 2020). Coercive control monitoring launched July 2024 under new offence.

### Courts & Corrections

| Source | URL | Notes |
|--------|-----|-------|
| [Judicial Commission (JIRS)](https://www.judcom.nsw.gov.au/judicial-information-research-system-jirs) | judcom.nsw.gov.au | Sentencing patterns by offence section |
| [ABS Corrective Services](https://www.abs.gov.au/statistics/people/crime-and-justice/corrective-services-australia/latest-release) | abs.gov.au | Quarterly imprisonment rates with state comparisons |
| [ICAC Investigation Reports](https://www.icac.nsw.gov.au) | icac.nsw.gov.au | Full corruption investigation archive as PDFs |
| [Legal Aid NSW Annual Reports](https://www.legalaid.nsw.gov.au) | legalaid.nsw.gov.au | 53,181 applications in 2022-23, 83.2% grant rate (PDF) |

---

## 🌿 Environment & Climate

### Air Quality

| Dataset | Format | Description |
|---------|--------|-------------|
| [NSW Air Quality API](https://www.airquality.nsw.gov.au/air-quality-data-services/air-quality-api) | REST/JSON - free, no key | Hourly data from entire monitoring network: O₃, NO₂, SO₂, CO, PM10, PM2.5 + meteorological. Since 1994. |
| [Air Quality Data Download](https://www.airquality.nsw.gov.au/air-quality-data-services/data-download-facility) | CSV export | Historical data back to 1994 by station/pollutant |

### Beach & Water

| Dataset | Format | Description |
|---------|--------|-------------|
| [Beachwatch](https://data.nsw.gov.au/data/dataset/beachwatch) | API, RSS, CSV (SEED) | 200+ swim sites since 1989 - daily pollution forecasts, weekly star ratings |
| WaterNSW Real-Time | [realtimedata.waternsw.com.au](https://realtimedata.waternsw.com.au) | Dam levels, river heights, blue-green algae alerts |
| [SharkSmart](https://sharksmart.nsw.gov.au) | App + push notifications | Tagged shark detections (37 listening stations), drone sightings (50+ beaches), SMART drumlines |
| Shark Meshing Program | Annual PDF (via DPI) | Catch data from nets at 51 beaches - target and non-target species |

### Bushfire

| Dataset | Format | Description |
|---------|--------|-------------|
| [RFS Current Incidents Feed](https://data.nsw.gov.au/data/dataset/nsw-rural-fire-service-current-incidents-feed) | **GeoJSON** | All current fires - 30-minute updates with location, alert level, polygon extent |
| [Fire Danger Ratings](https://data.nsw.gov.au/data/organization/nsw-rural-fire-service) | Feed | Current fire danger by district |
| [Bush Fire Prone Land](https://data.nsw.gov.au/data/dataset/bush-fire-prone-land) | Shapefile, WMS (via SEED) | "Is your property in a bushfire zone?" |
| Fire Extent & Severity (2019-20) | SEED | Black Summer fire mapping |

### Flood

| Source | URL | Description |
|--------|-----|-------------|
| [NSW Flood Data Portal](https://www.environment.nsw.gov.au/topics/water/floodplains/nsw-flood-data-portal) | flooddata.ses.nsw.gov.au | 2,300+ datasets from 120+ orgs: studies, extent mapping, model outputs |
| [EPI Flood Layer](https://datasets.seed.nsw.gov.au/dataset/epi-flood) | Shapefile, WMS, WFS | Land with flood-related development restrictions |
| [Flood-tagged datasets on Data.NSW](https://data.nsw.gov.au/data/dataset?tags=Flood) | Various | Aggregated flood data across agencies |

### Climate & Energy

| Dataset | Format | Description |
|---------|--------|-------------|
| [NARCliM2.0](https://datasets.seed.nsw.gov.au/dataset/climate-change-in-nsw) | GeoTIFF, ArcGIS REST | NSW climate projections at **4km resolution** - temperature, rainfall, hot days, fire weather to 2100 |
| [AEMO NEM Dashboard](https://www.aemo.com.au/energy-systems/electricity/national-electricity-market-nem/data-nem/data-dashboard-nem) | 5-min interval data | Real-time electricity generation by fuel source (NSW region) |
| [CER Solar Installations by Postcode](https://cer.gov.au/markets/reports-and-data/small-scale-installation-postcode-data) | CSV | Monthly solar panel installations by postcode |

### Biodiversity

| Dataset | Format | Description |
|---------|--------|-------------|
| [BioNet Atlas](https://www.environment.nsw.gov.au/topics/animals-and-plants/biodiversity/nsw-bionet/about-bionet-atlas) | [OData REST API](https://www.environment.nsw.gov.au/topics/animals-and-plants/biodiversity/nsw-bionet/web-services) | **13+ million** species observation records |
| [BioNet Species Sightings (SEED)](https://datasets.seed.nsw.gov.au/dataset/nsw-bionet-species-sightings-data-collection8a9c4) | SEED download | Bulk download of sightings collection |
| [BioNet Vegetation Maps (SEED)](https://datasets.seed.nsw.gov.au/dataset/nsw-bionet-vegetation-map-catalogue-collection36515) | SEED download | Statewide vegetation mapping |
| [Threatened Biodiversity Profiles](https://www.environment.nsw.gov.au/topics/animals-and-plants/biodiversity/nsw-bionet/about-bionet-atlas/threatened-biodiversity-profiles) | Web profiles | Detailed profiles for listed species |
| Koala Habitat Information Base | SEED | Koala habitat likelihood mapping |

### Pollution

| Dataset | Format | Description |
|---------|--------|-------------|
| [National Pollutant Inventory](https://www.dcceew.gov.au/about/news/national-pollutant-inventory-data-2022-23-now-available) | CSV/web search | Annual emissions of 93 toxic substances from 900+ NSW industrial facilities |
| [EPA Contaminated Land](https://www.epa.nsw.gov.au/Your-environment/Contaminated-land/notified-and-regulated-contaminated-land/list-of-notified-sites) | Searchable DB + Excel/PDF | Every notified potentially contaminated site |

---

## 💸 Fines & Revenue

**Revenue NSW** publishes individual XLSX files for virtually every fine type at [revenue.nsw.gov.au/help-centre/resources-library/statistics](https://revenue.nsw.gov.au/help-centre/resources-library/statistics):

| Dataset | Format | Description |
|---------|--------|-------------|
| Speed/red-light camera offences | XLSX (~3.2MB) | By individual camera, location, financial year, zone type |
| Parking offences | XLSX | By issuing authority and year |
| Mobile phone offences | XLSX | By police area command |
| Seat belt offences | XLSX | By police area command |
| Food safety infringements | XLSX | By offence type |
| Criminal infringement notices | XLSX | By offence type |
| Master penalty notice data | XLSX (~4-5MB each) | 2022-2026 comprehensive datasets |

Also on Data.NSW: [datasets tagged "fines"](https://data.nsw.gov.au/data/dataset/?tags=fines) including all penalty notice types (T-way lane, unregistered driving, smoking, etc.)

---

## 🎰 Gambling

| Dataset | Source | Format | Description |
|---------|--------|--------|-------------|
| Gaming Machine Data Reports | [nsw.gov.au/.../gaming-machine-data-reports](https://www.nsw.gov.au/business-and-economy/liquor-and-gaming/gaming/gaming-machine-data-reports) | Quarterly XLSX | **Net profit (community losses) by LGA** - $2.45 billion in Q3 2025 alone |
| Licensed Premises Data | Liquor & Gaming NSW (Data.NSW) | XLSX (~4.5MB, monthly) | Every licensed venue: name, address, geocodes, trading hours, **number of poker machines per venue** |
| [Liquor Licence Register](https://researchdata.edu.au/liquor-licence-premises-list/1461488) | XLSX | Complete register with licence types and conditions |

---

## 🍽 Food Safety

| Source | URL | Description |
|--------|-----|-------------|
| [Scores on Doors](https://www.foodauthority.nsw.gov.au) | Per-council web pages | 3-5 star hygiene ratings for restaurants/cafes (participating councils) |
| [Name & Shame Register](https://www.foodauthority.nsw.gov.au/offences) | Weekly HTML | Businesses fined or prosecuted for food safety violations |
| Revenue NSW food safety fines | XLSX | Penalty notices for food safety offences by type |

No unified downloadable dataset exists - scraping across councils required. Think NYC's restaurant letter grade system but for Sydney.

---

## 🎓 Education

| Dataset | Source | Format | Description |
|---------|--------|--------|-------------|
| [MySchool](https://myschool.edu.au) | ACARA | Web only | School-level performance (NAPLAN), ICSEA, enrolments, attendance, finances. Bulk access via ACARA Data Access Program. |
| NSW School Master Dataset | [Data.NSW](https://data.nsw.gov.au/data/organization/education) | CSV | All government schools: locations, lat/long, type, enrolments |
| Student Headcount by School | Data.NSW | CSV | Historical enrolments per school since 2004 |
| VET / Smart and Skilled | Data.NSW | CSV/Excel | Commencements, completions 2015-2026, apprenticeships by industry |
| TAFE NSW Annual Reports | parliament.nsw.gov.au | **PDF** | Enrolment data, completion rates, demographics. PDF extraction needed. |
| ACECQA National Register | acecqa.gov.au | Searchable DB + download | Every childcare/OSHC with quality ratings |

---

## 📊 Demographics & Economics

| Dataset | Source | Format | Description |
|---------|--------|--------|-------------|
| [ABS Data by Region](https://www.abs.gov.au/databyregion) | ABS | Web + API | NSW population by SA2/LGA, Census DataPacks at SA1 |
| NSW Population Projections | planning.nsw.gov.au | Excel | Projected growth to 2041 by LGA and SA2 (10.07 million by 2041) |
| NSW Budget Open Data | budget.nsw.gov.au | Excel | All government financial statements (CC BY) |
| [Urban Heat & Canopy Data](https://www.planning.nsw.gov.au/policy-and-legislation/urban-greening/urban-heat-and-canopy-data) | XLSX + raster | Tree canopy cover by LGA/suburb (21.7% avg, 2016-2022 trends) |
| SIRA Open Data | sira.nsw.gov.au/open-data-schemes | Power BI + Excel | CTP insurance, Workers Comp, Home Building Comp scheme data |
| [NSW Hansard](https://parliament.nsw.gov.au/hansard) | HTML + scanned PDFs (from 1880) | Every parliamentary speech. NLP/policy tracking goldmine. |

---

## 🗺 Geospatial Foundation

NSW Foundation Spatial Data Framework (~300 datasets across 10 themes) via the [Spatial Collaboration Portal](https://portal.spatial.nsw.gov.au):

| Theme | Key Content | Format |
|-------|------------|--------|
| Administrative Boundaries | Parish, county, suburb, LGA, electoral, ABS boundaries | WMS, WFS, Shapefile |
| Cadastre | Every property boundary (daily updates) | WMS, WFS, FGDB |
| Geocoded Addressing (G-NAF) | 15.9 million geocoded addresses (free until mid-2029) | PSV, FGDB, API |
| Transport | Road centrelines, rail, ferry routes | WMS, WFS, Shapefile |
| Elevation & Depth | 1m/2m/5m DEMs from LiDAR via [ELVIS](https://elevation.fsdf.org.au) | GeoTIFF, LAS/LAZ |
| Imagery | Current ortho + **Historical Imagery Viewer** (600,000+ aerial frames, free 600dpi) | WMS, TIFF |
| Place Names | Geographical Names Register | WFS, web |
| Water | Rivers, streams, lakes, water bodies | WMS, WFS, Shapefile |
| Land Cover | Vegetation and land use classification | WMS |
| Positioning | Survey marks, CORSnet-NSW stations | WMS, WFS |

---

## 📄 PDF-Trapped Data Worth Liberating

Some of the most interesting data exists only in PDFs or clunky web interfaces. Building tools to surface this adds massive value.

| Data | Where | Why it's worth it |
|------|-------|-------------------|
| Ambulance response times by SA3 | BHI quarterly PDF supplements | Nobody has a clean suburb-searchable map |
| Seclusion/restraint by hospital | BHI quarterly PDF supplements | Hospital-by-hospital mental health practices over time |
| Dog attack statistics | Office of Local Government quarterly PDFs | Council-by-council trends in attacks and euthanasia rates |
| TAFE enrolments & completions | Parliamentary annual reports | Skills pipeline data |
| Recreational fishing survey | DPI PDFs (up to 21MB) | Catch by species by region. Interactive map potential. |
| NSW Crime Commission reports | Annual report PDFs | Drug seizures, criminal assets, organized crime trends |
| ICAC investigation reports | Individual PDFs | Complete corruption archive |
| [NSW Hansard (pre-digital)](https://parliament.nsw.gov.au/hansard) | Scanned PDFs from 1880 | Historical parliamentary speech analysis |
| EPA GIPA disclosure logs | Individual agency websites | FOI release archive |
| State Archives convict records | nsw.gov.au (State Records NSW) | Colonial-era records, partially digitized |

---

## Contributing

Contributions welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first.

If you find a NSW government dataset that's not listed here, please open a PR or issue. Especially interested in:

- Datasets we've missed entirely
- URL corrections (government links break constantly)
- Format/access updates
- New project ideas with specific data source references

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the authors have waived all copyright and related rights to this work.
