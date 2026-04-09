<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Global Emergency Alert Directory</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.9/babel.min.js"></script>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'DM Sans', 'Segoe UI', sans-serif; background: #0d1117; color: #c9d1d9; }
  a { text-decoration: none; color: inherit; }
  button { font-family: inherit; }
  #root { min-height: 100vh; }

  .header { background: linear-gradient(135deg, #161b22 0%, #0d1117 50%, #1a1025 100%); border-bottom: 1px solid #21262d; padding: 28px 24px 20px; }
  .header-inner { max-width: 1100px; margin: 0 auto; }
  .header-row { display: flex; align-items: center; gap: 12px; margin-bottom: 6px; }
  .header-row span { font-size: 28px; }
  .header-row h1 { font-size: 22px; font-weight: 700; color: #e6edf3; letter-spacing: -0.3px; }
  .header-sub { margin: 4px 0 0 40px; font-size: 13px; color: #8b949e; }

  .controls { background: #161b22; border-bottom: 1px solid #21262d; padding: 14px 24px; position: sticky; top: 0; z-index: 100; }
  .controls-inner { max-width: 1100px; margin: 0 auto; display: flex; flex-wrap: wrap; gap: 10px; align-items: center; }
  .search-wrap { position: relative; flex: 1 1 240px; min-width: 200px; }
  .search-wrap span { position: absolute; left: 10px; top: 50%; transform: translateY(-50%); font-size: 14px; color: #484f58; }
  .search-wrap input { width: 100%; padding: 8px 12px 8px 32px; background: #0d1117; border: 1px solid #30363d; border-radius: 8px; color: #c9d1d9; font-size: 13px; outline: none; font-family: inherit; }
  .search-wrap input::placeholder { color: #484f58; }
  .type-filters { display: flex; gap: 4px; flex-wrap: wrap; }

  .pill { padding: 6px 12px; border-radius: 20px; border: 1px solid #30363d; background: transparent; color: #8b949e; font-size: 12px; font-weight: 500; cursor: pointer; }
  .pill.active { border-color: #58a6ff; background: rgba(88,166,255,0.12); color: #58a6ff; }

  .region-pills { padding: 14px 24px 4px; max-width: 1100px; margin: 0 auto; display: flex; gap: 6px; flex-wrap: wrap; }
  .rpill { padding: 5px 12px; border-radius: 6px; border: 1px solid #30363d; background: #161b22; color: #8b949e; font-size: 12px; cursor: pointer; font-weight: 500; }
  .rpill.active { border-color: #58a6ff; background: rgba(88,166,255,0.08); color: #58a6ff; }

  .content { max-width: 1100px; margin: 0 auto; padding: 16px 24px 40px; }
  .empty { text-align: center; padding: 60px 20px; color: #484f58; }
  .empty div { font-size: 40px; margin-bottom: 12px; }

  .region-block { margin-bottom: 24px; }
  .region-header { display: flex; align-items: center; gap: 10px; margin-bottom: 10px; padding: 8px 0; }
  .region-header span.emoji { font-size: 20px; }
  .region-header h2 { font-size: 16px; font-weight: 700; color: #e6edf3; }
  .region-count { font-size: 11px; padding: 2px 8px; border-radius: 10px; font-family: 'JetBrains Mono', monospace; font-weight: 500; }

  .alert-list { display: flex; flex-direction: column; gap: 4px; }
  .alert-row { display: grid; grid-template-columns: minmax(140px, 200px) 1fr auto auto; align-items: center; gap: 12px; padding: 10px 14px; background: #161b22; border: 1px solid #21262d; border-radius: 8px; transition: border-color 0.15s, background 0.15s; }
  .alert-row:hover { border-color: #30363d; background: #1c2129; }
  .alert-scope { font-size: 11px; color: #8b949e; font-family: 'JetBrains Mono', monospace; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .alert-name { font-size: 13px; font-weight: 500; color: #58a6ff; }
  .alert-badge { font-size: 10px; padding: 2px 8px; border-radius: 10px; white-space: nowrap; font-weight: 500; }
  .alert-cities { font-size: 11px; color: #6e7681; max-width: 200px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

  .show-toggle { margin-top: 8px; padding: 5px 14px; background: transparent; border: 1px solid #21262d; border-radius: 6px; color: #58a6ff; font-size: 12px; cursor: pointer; }

  @media (max-width: 700px) {
    .alert-row { grid-template-columns: 1fr; gap: 4px; }
    .alert-cities { max-width: none; }
  }
</style>
</head>
<body>
<div id="root"></div>
<script type="text/babel">
const { useState, useMemo } = React;

const REGIONS = [
  {
    id: "us", name: "United States", emoji: "\u{1f1fa}\u{1f1f8}", color: "#1a3a5c",
    alerts: [
      { scope: "National", name: "FEMA App", url: "https://www.fema.gov/about/news-multimedia/mobile-products", type: "weather", cities: "All US cities" },
      { scope: "National", name: "Wireless Emergency Alerts (WEA)", url: "https://www.fcc.gov/public-safety-and-homeland-security/policy-and-licensing-division/alerting/general/wireless", type: "both", cities: "All US cities (cell broadcast)" },
      { scope: "State \u2013 GA", name: "Ready Georgia", url: "https://gema.georgia.gov/", type: "both", cities: "Atlanta" },
      { scope: "State \u2013 NY", name: "NY-Alert", url: "https://alert.ny.gov/", type: "both", cities: "New York" },
      { scope: "State \u2013 CA", name: "MyShake (Earthquake Early Warning)", url: "https://myshake.berkeley.edu/", type: "weather", cities: "Irvine, Palo Alto, San Francisco" },
      { scope: "State \u2013 WA", name: "Washington EMD Alerts", url: "https://mil.wa.gov/alerts", type: "both", cities: "Bellevue, Seattle" },
      { scope: "State \u2013 NC", name: "Ready NC", url: "https://www.readync.gov/stay-informed/emergency-alerts", type: "weather", cities: "Raleigh" },
      { scope: "City \u2013 Atlanta", name: "NotifyATL / FALCON (Fulton County)", url: "https://www.fultoncountyga.gov/emergency-management", type: "both", cities: "Atlanta" },
      { scope: "City \u2013 Austin", name: "Warn Central Texas", url: "https://www.warncentraltexas.org/", type: "both", cities: "Austin" },
      { scope: "City \u2013 Chicago", name: "Chicago OEMC / NotifyChicago", url: "https://www.chicago.gov/city/en/depts/oem.html", type: "both", cities: "Chicago" },
      { scope: "City \u2013 Dallas", name: "DallasAlert", url: "https://dallascityhall.com/departments/officeemergencymanagement/Pages/Dallas-Alert.aspx", type: "both", cities: "Dallas" },
      { scope: "City \u2013 Denver", name: "Denver Emergency Notification", url: "https://www.denvergov.org/Government/Agencies-Departments-Offices/Denver-Office-of-Emergency-Management", type: "both", cities: "Denver" },
      { scope: "City \u2013 Indianapolis", name: "Alert Marion County", url: "https://www.indy.gov/agency/office-of-public-health-and-safety", type: "both", cities: "Indianapolis" },
      { scope: "City \u2013 Irvine", name: "AlertOC (Orange County)", url: "https://cityofirvine.org/office-emergency-management/stay-informed-alertoc", type: "both", cities: "Irvine" },
      { scope: "City \u2013 New York", name: "Notify NYC", url: "https://a858-nycnotify.nyc.gov/notifynyc/", type: "both", cities: "New York" },
      { scope: "City \u2013 McLean/Fairfax", name: "Fairfax Alerts (CEAN)", url: "https://www.fairfaxcounty.gov/alerts", type: "both", cities: "McLean" },
      { scope: "City \u2013 Palo Alto", name: "AlertSCC (Santa Clara County)", url: "https://www.sccgov.org/sites/oes/alertscc", type: "both", cities: "Palo Alto" },
      { scope: "City \u2013 Raleigh", name: "ReadyWake (Wake County)", url: "https://www.wake.gov/departments-government/fire-services-emergency-management/emergency-management/alerts-notifications-and-warnings", type: "both", cities: "Raleigh" },
      { scope: "City \u2013 San Francisco", name: "AlertSF", url: "https://sfdem.org/alertsf", type: "both", cities: "San Francisco" },
      { scope: "City \u2013 Seattle", name: "AlertSeattle", url: "https://www.seattle.gov/emergency-management/alertseattle", type: "both", cities: "Seattle" },
      { scope: "City \u2013 Washington DC", name: "AlertDC", url: "https://hsema.dc.gov/page/alertdc", type: "both", cities: "Washington, DC" },
      { scope: "City \u2013 Boston (Metro Hub, MA)", name: "AlertBoston", url: "https://www.boston.gov/departments/emergency-management/city-boston-alerts-and-notifications", type: "both", cities: "Metro Hub, MA" },
    ],
  },
  {
    id: "ca", name: "Canada", emoji: "\u{1f1e8}\u{1f1e6}", color: "#8b1a1a",
    alerts: [
      { scope: "National", name: "Alert Ready (Cell Broadcast)", url: "https://www.alertready.ca/", type: "both", cities: "All Canadian cities" },
      { scope: "National", name: "WeatherCAN (Environment Canada)", url: "https://www.canada.ca/en/environment-climate-change/services/weather-general-tools-resources/weathercan.html", type: "weather", cities: "All Canadian cities" },
      { scope: "City \u2013 Vancouver", name: "Alertable (City of Vancouver)", url: "https://vancouver.ca/home-property-development/alertable-public-alerting-system.aspx", type: "both", cities: "Vancouver" },
    ],
  },
  {
    id: "latam", name: "Latin America", emoji: "\u{1f30e}", color: "#2d6a4f",
    alerts: [
      { scope: "Mexico \u2013 National", name: "SASSLA (Seismic Alert)", url: "https://www.sassla.mx/", type: "weather", cities: "Mexico City" },
      { scope: "Mexico \u2013 National", name: "SkyAlert", url: "https://www.skyalert.mx/", type: "weather", cities: "Mexico City" },
      { scope: "Mexico \u2013 City", name: "911 CDMX App", url: "https://www.c5.cdmx.gob.mx/", type: "both", cities: "Mexico City" },
      { scope: "Chile \u2013 National", name: "SAE Cell Broadcast", url: "https://www.onemi.gov.cl/alerta-de-emergencia/", type: "both", cities: "Santiago (no app)" },
      { scope: "Brazil \u2013 National", name: "Defesa Civil Alerta (Cell Broadcast)", url: "https://www.gov.br/defesacivil/", type: "both", cities: "S\u00e3o Paulo" },
      { scope: "Brazil \u2013 State", name: "Alerta SP (S\u00e3o Paulo State)", url: "https://www.defesacivil.sp.gov.br/", type: "weather", cities: "S\u00e3o Paulo" },
      { scope: "Argentina \u2013 National", name: "AlertAR (Cell Broadcast, pilot)", url: "https://www.argentina.gob.ar/sinagir", type: "both", cities: "Buenos Aires" },
      { scope: "Colombia \u2013 Bogot\u00e1", name: "IDIGER Alert System (Bogot\u00e1)", url: "https://www.idiger.gov.co/", type: "weather", cities: "Bogot\u00e1" },
      { scope: "Colombia \u2013 Medell\u00edn", name: "App SIATA (Aburr\u00e1 Valley)", url: "https://siata.gov.co/", type: "weather", cities: "Medell\u00edn" },
    ],
  },
  {
    id: "oceania", name: "Australia & New Zealand", emoji: "\u{1f1e6}\u{1f1fa}", color: "#b5651d",
    alerts: [
      { scope: "AU \u2013 National", name: "Emergency+ App", url: "https://www.triplezero.gov.au/triple-zero/emergency-plus-app", type: "security", cities: "All AU cities" },
      { scope: "AU \u2013 SA", name: "Alert SA", url: "https://www.alert.sa.gov.au/", type: "both", cities: "Adelaide" },
      { scope: "AU \u2013 VIC", name: "VicEmergency", url: "https://www.emergency.vic.gov.au/respond/", type: "both", cities: "Melbourne" },
      { scope: "AU \u2013 NSW", name: "Hazards Near Me NSW", url: "https://www.nsw.gov.au/emergency/hazards-near-me-nsw", type: "both", cities: "Sydney, Canberra" },
      { scope: "AU \u2013 WA", name: "Emergency WA", url: "https://www.emergency.wa.gov.au/", type: "both", cities: "Perth" },
      { scope: "AU \u2013 QLD", name: "BOM Weather App + SES QLD", url: "http://www.bom.gov.au/app/", type: "weather", cities: "Brisbane" },
      { scope: "NZ \u2013 National", name: "Emergency Mobile Alert (Cell Broadcast)", url: "https://getready.govt.nz/emergency-mobile-alert/", type: "both", cities: "Auckland, Wellington" },
      { scope: "NZ \u2013 National", name: "GeoNet (Earthquakes/Volcanoes)", url: "https://www.geonet.org.nz/", type: "weather", cities: "Auckland, Wellington" },
      { scope: "NZ \u2013 National", name: "MetService (Weather)", url: "https://www.metservice.com/", type: "weather", cities: "Auckland, Wellington" },
    ],
  },
  {
    id: "asia", name: "Asia", emoji: "\u{1f30f}", color: "#4a148c",
    alerts: [
      { scope: "South Korea", name: "Emergency Ready App", url: "https://www.mois.go.kr/eng/", type: "both", cities: "Seoul" },
      { scope: "South Korea", name: "SafeKorea", url: "https://www.safekorea.go.kr/", type: "both", cities: "Seoul" },
      { scope: "Singapore", name: "SGSecure", url: "https://www.sgsecure.gov.sg/", type: "security", cities: "Singapore" },
      { scope: "Singapore", name: "myENV (Weather/Floods)", url: "https://www.nea.gov.sg/", type: "weather", cities: "Singapore" },
      { scope: "Taiwan", name: "CWA Earthquake App", url: "https://www.cwa.gov.tw/eng/", type: "weather", cities: "Taipei" },
      { scope: "Thailand", name: "Thai Disaster Alert (THDA)", url: "https://www.disaster.go.th/", type: "both", cities: "Bangkok" },
      { scope: "Indonesia", name: "Info BMKG", url: "https://www.bmkg.go.id/", type: "both", cities: "Jakarta" },
      { scope: "Philippines", name: "NDRRMC (Cell Broadcast/SMS)", url: "https://ndrrmc.gov.ph/", type: "both", cities: "Manila" },
    ],
  },
  {
    id: "japan", name: "Japan", emoji: "\u{1f1ef}\u{1f1f5}", color: "#c62828",
    alerts: [
      { scope: "National", name: "Safety Tips (JNTO, 15 languages)", url: "https://www.jnto.go.jp/safety-tips/eng/app.html", type: "both", cities: "All Japan cities" },
      { scope: "National", name: "NERV Disaster Prevention", url: "https://nerv.app/en/", type: "both", cities: "All Japan cities" },
      { scope: "National", name: "NHK WORLD-JAPAN (11 languages)", url: "https://www3.nhk.or.jp/nhkworld/", type: "both", cities: "All Japan cities" },
      { scope: "National", name: "Yahoo!\u9632\u707d\u901f\u5831 (Japanese)", url: "https://emg.yahoo.co.jp/", type: "both", cities: "All Japan cities" },
      { scope: "City \u2013 Tokyo", name: "Disaster Preparedness Tokyo", url: "https://www.bousai.metro.tokyo.lg.jp/", type: "both", cities: "Tokyo" },
      { scope: "Prefecture \u2013 Osaka", name: "Osaka Disaster Prevention", url: "https://www.pref.osaka.lg.jp/o090050/kikikanri/bousaiapp.html", type: "both", cities: "Osaka" },
      { scope: "City \u2013 Nagoya", name: "Nagoya City Disaster Prevention App", url: "https://www.city.nagoya.jp/", type: "both", cities: "Nagoya" },
      { scope: "Prefecture \u2013 Hiroshima", name: "Hiroshima Emergency Evacuation Guide", url: "https://www.pref.hiroshima.lg.jp/", type: "both", cities: "Hiroshima" },
      { scope: "Prefecture \u2013 Wakayama", name: "Wakayama Disaster Navi", url: "https://www.pref.wakayama.lg.jp/", type: "weather", cities: "Shirahama" },
      { scope: "Prefecture \u2013 Fukuoka", name: "Fukuoka Disaster Navi Mamoru-kun", url: "https://www.pref.fukuoka.lg.jp/", type: "both", cities: "Fukuoka" },
    ],
  },
  {
    id: "europe", name: "Europe", emoji: "\u{1f1ea}\u{1f1fa}", color: "#1a237e",
    alerts: [
      { scope: "Germany", name: "NINA (BBK Warning App)", url: "https://www.bbk.bund.de/DE/Warnung-Vorsorge/Warn-App-NINA/warn-app-nina_node.html", type: "both", cities: "Berlin, D\u00fcsseldorf, Frankfurt, Jena, Mannheim, Munich" },
      { scope: "Germany", name: "KATWARN", url: "https://www.katwarn.de/en/", type: "both", cities: "All German cities" },
      { scope: "Germany", name: "WarnWetter (DWD)", url: "https://www.dwd.de/EN/ourservices/warnwetterapp/warnwetterapp.html", type: "weather", cities: "All German cities" },
      { scope: "Switzerland", name: "Alertswiss", url: "https://www.alert.swiss/en/home.html", type: "both", cities: "Lausanne, Zurich" },
      { scope: "France", name: "FR-Alert (Cell Broadcast)", url: "https://www.gouvernement.fr/fr-alert", type: "both", cities: "Grenoble, Lyon, Marseille, Nantes, Paris" },
      { scope: "France", name: "M\u00e9t\u00e9o-France (Weather)", url: "https://meteofrance.com/", type: "weather", cities: "All French cities" },
      { scope: "Netherlands", name: "NL-Alert (Cell Broadcast)", url: "https://www.government.nl/topics/counterterrorism-and-national-security/nl-alert", type: "both", cities: "Amsterdam" },
      { scope: "Belgium", name: "BE-Alert", url: "https://www.be-alert.be/en", type: "both", cities: "Brussels" },
      { scope: "Belgium", name: "112 BE App", url: "https://www.sos112.be/en", type: "security", cities: "Brussels" },
      { scope: "Denmark", name: "S!RENEN (Cell Broadcast)", url: "https://www.televirke.dk/", type: "both", cities: "Copenhagen" },
      { scope: "Finland", name: "112 Suomi", url: "https://112.fi/en/112-suomi-application", type: "both", cities: "Espoo" },
      { scope: "Norway", name: "N\u00f8dvarsel (Cell Broadcast)", url: "https://www.televirke.no/", type: "both", cities: "Oslo" },
      { scope: "Sweden", name: "Krisinformation.se", url: "https://www.krisinformation.se/en", type: "both", cities: "Stockholm" },
      { scope: "UK", name: "UK Emergency Alerts (Cell Broadcast)", url: "https://www.gov.uk/alerts", type: "both", cities: "London, Manchester" },
      { scope: "UK", name: "Met Office Weather", url: "https://www.metoffice.gov.uk/", type: "weather", cities: "London, Manchester" },
      { scope: "Ireland", name: "Met \u00c9ireann", url: "https://www.met.ie/", type: "weather", cities: "Dublin" },
      { scope: "Spain", name: "ES-Alert (Cell Broadcast)", url: "https://www.proteccioncivil.es/", type: "both", cities: "Barcelona, Madrid" },
      { scope: "Spain", name: "AlertCops (Security)", url: "https://alertcops.ses.mir.es/mialertcops/en/", type: "security", cities: "Barcelona, Madrid" },
      { scope: "Spain", name: "AEMET (Weather)", url: "https://www.aemet.es/", type: "weather", cities: "Barcelona, Madrid" },
      { scope: "Italy", name: "IT-Alert (Cell Broadcast)", url: "https://www.it-alert.it/en/", type: "both", cities: "Milan, Rome" },
      { scope: "Portugal", name: "Meteo@IPMA", url: "https://www.ipma.pt/en/", type: "weather", cities: "Lisbon" },
      { scope: "Austria", name: "AT-Alert + KATWARN Austria", url: "https://www.katwarn.at/", type: "both", cities: "Vienna" },
      { scope: "Austria \u2013 Vienna", name: "Stadt Wien App", url: "https://www.wien.gv.at/", type: "both", cities: "Vienna" },
    ],
  },
  {
    id: "mideast", name: "Middle East", emoji: "\u{1f54c}", color: "#5d4037",
    alerts: [
      { scope: "Israel \u2013 National", name: "Home Front Command (Pikud HaOref)", url: "https://www.oref.org.il/en", type: "both", cities: "Nazareth, Tel Aviv" },
      { scope: "Israel \u2013 National", name: "RedAlert / Tzofar", url: "https://apps.apple.com/il/app/tzofar-red-alert/id1480129320", type: "security", cities: "Nazareth, Tel Aviv" },
      { scope: "Israel \u2013 Tel Aviv", name: "DigiTel (Municipal)", url: "https://www.tel-aviv.gov.il/en/residents/pages/digitel.aspx", type: "both", cities: "Tel Aviv" },
      { scope: "Saudi Arabia", name: "Saudi Civil Defense Early Warning", url: "https://998.gov.sa/English/Pages/Automatic-Early-Warning.aspx", type: "both", cities: "Riyadh" },
      { scope: "Saudi Arabia", name: "Tawakkalna (Super App)", url: "https://ta.sdaia.gov.sa/", type: "both", cities: "Riyadh" },
      { scope: "Saudi Arabia", name: "Kollona Amn", url: "https://www.moi.gov.sa/", type: "security", cities: "Riyadh" },
      { scope: "UAE \u2013 National", name: "UAE Early Warning (Cell Broadcast)", url: "https://www.ncema.gov.ae/en", type: "both", cities: "Dubai" },
      { scope: "UAE \u2013 Dubai", name: "Dubai Police App", url: "https://www.dubaipolice.gov.ae/", type: "security", cities: "Dubai" },
    ],
  },
  {
    id: "africa", name: "Africa", emoji: "\u{1f30d}", color: "#e65100",
    alerts: [
      { scope: "South Africa", name: "WeatherSmart (SAWS)", url: "https://www.weathersa.co.za/", type: "weather", cities: "Johannesburg" },
      { scope: "South Africa \u2013 Gauteng", name: "e-Panic Button App", url: "https://www.gauteng.gov.za/", type: "security", cities: "Johannesburg" },
      { scope: "Morocco", name: "Vigilance Maroc-M\u00e9t\u00e9o (web only)", url: "https://vigilance.marocmeteo.ma/", type: "weather", cities: "Casablanca" },
    ],
  },
  {
    id: "india", name: "India", emoji: "\u{1f1ee}\u{1f1f3}", color: "#f57f17",
    alerts: [
      { scope: "National", name: "SACHET (NDMA Disaster Alerts)", url: "https://sachet.ndma.gov.in/", type: "both", cities: "All Indian cities" },
      { scope: "National", name: "Mausam (IMD Weather)", url: "https://mausam.imd.gov.in/", type: "weather", cities: "All Indian cities" },
      { scope: "National", name: "Damini (Lightning Alerts)", url: "https://damini.iitm.ac.in/", type: "weather", cities: "All Indian cities" },
      { scope: "National", name: "BhooKamp (Earthquake Monitoring)", url: "https://riseq.seismo.gov.in/", type: "weather", cities: "All Indian cities" },
      { scope: "City \u2013 Mumbai", name: "Disaster Management BMC", url: "https://dm.mcgm.gov.in/", type: "both", cities: "Mumbai" },
      { scope: "City \u2013 Mumbai", name: "Mumbai Flood App (IIT Bombay)", url: "https://www.mumbaiflood.in/", type: "weather", cities: "Mumbai" },
    ],
  },
];

const TYPE_LABELS = { weather: "Weather", security: "Security", both: "Weather & Security" };
const TYPE_COLORS = { weather: "#2196f3", security: "#e53935", both: "#7b1fa2" };

function App() {
  const [search, setSearch] = useState("");
  const [activeRegion, setActiveRegion] = useState(null);
  const [typeFilter, setTypeFilter] = useState("all");
  const [expandedCards, setExpandedCards] = useState({});

  const filtered = useMemo(() => {
    const q = search.toLowerCase();
    return REGIONS.map((r) => {
      if (activeRegion && r.id !== activeRegion) return null;
      const alerts = r.alerts.filter((a) => {
        if (typeFilter !== "all" && a.type !== typeFilter && a.type !== "both") return false;
        if (!q) return true;
        return a.name.toLowerCase().includes(q) || a.scope.toLowerCase().includes(q) || a.cities.toLowerCase().includes(q) || r.name.toLowerCase().includes(q);
      });
      if (alerts.length === 0) return null;
      return { ...r, alerts };
    }).filter(Boolean);
  }, [search, activeRegion, typeFilter]);

  const totalLinks = filtered.reduce((s, r) => s + r.alerts.length, 0);
  const toggleExpand = (id) => setExpandedCards((p) => ({ ...p, [id]: !p[id] }));

  return React.createElement("div", null,
    React.createElement("div", { className: "header" },
      React.createElement("div", { className: "header-inner" },
        React.createElement("div", { className: "header-row" },
          React.createElement("span", null, "\u{1f6a8}"),
          React.createElement("h1", null, "Global Emergency Alert Directory")
        ),
        React.createElement("p", { className: "header-sub" }, totalLinks + " alert systems across " + filtered.length + " regions")
      )
    ),
    React.createElement("div", { className: "controls" },
      React.createElement("div", { className: "controls-inner" },
        React.createElement("div", { className: "search-wrap" },
          React.createElement("span", null, "\u{1f50d}"),
          React.createElement("input", { type: "text", placeholder: "Search city, country, or app name\u2026", value: search, onChange: (e) => setSearch(e.target.value) })
        ),
        React.createElement("div", { className: "type-filters" },
          [{ k: "all", l: "All Types" }, { k: "weather", l: "\u{1f326} Weather" }, { k: "security", l: "\u{1f6e1} Security" }].map(({ k, l }) =>
            React.createElement("button", { key: k, className: "pill" + (typeFilter === k ? " active" : ""), onClick: () => setTypeFilter(k) }, l)
          )
        )
      )
    ),
    React.createElement("div", { className: "region-pills" },
      React.createElement("button", { className: "rpill" + (!activeRegion ? " active" : ""), onClick: () => setActiveRegion(null) }, "All Regions"),
      REGIONS.map((r) =>
        React.createElement("button", { key: r.id, className: "rpill" + (activeRegion === r.id ? " active" : ""), onClick: () => setActiveRegion(activeRegion === r.id ? null : r.id) }, r.emoji + " " + r.name)
      )
    ),
    React.createElement("div", { className: "content" },
      filtered.length === 0 && React.createElement("div", { className: "empty" },
        React.createElement("div", null, "\u{1f50e}"),
        React.createElement("p", null, "No results found. Try a different search term.")
      ),
      filtered.map((region) => {
        const isExpanded = expandedCards[region.id] !== false;
        const showToggle = region.alerts.length > 5;
        const visible = isExpanded ? region.alerts : region.alerts.slice(0, 5);
        return React.createElement("div", { key: region.id, className: "region-block" },
          React.createElement("div", { className: "region-header", style: { borderBottom: "2px solid " + region.color + "44" } },
            React.createElement("span", { className: "emoji" }, region.emoji),
            React.createElement("h2", null, region.name),
            React.createElement("span", { className: "region-count", style: { background: region.color + "22", color: region.color + "cc", border: "1px solid " + region.color + "44" } }, region.alerts.length)
          ),
          React.createElement("div", { className: "alert-list" },
            visible.map((alert, i) =>
              React.createElement("a", { key: i, href: alert.url, target: "_blank", rel: "noopener noreferrer", className: "alert-row" },
                React.createElement("span", { className: "alert-scope" }, alert.scope),
                React.createElement("span", { className: "alert-name" }, alert.name),
                React.createElement("span", { className: "alert-badge", style: { background: TYPE_COLORS[alert.type] + "18", color: TYPE_COLORS[alert.type], border: "1px solid " + TYPE_COLORS[alert.type] + "33" } }, TYPE_LABELS[alert.type]),
                React.createElement("span", { className: "alert-cities" }, alert.cities)
              )
            )
          ),
          showToggle && React.createElement("button", { className: "show-toggle", onClick: () => toggleExpand(region.id) }, isExpanded ? "Show less \u25b4" : "Show all " + region.alerts.length + " \u25be")
        );
      })
    )
  );
}

ReactDOM.createRoot(document.getElementById("root")).render(React.createElement(App));
</script>
</body>
</html>
