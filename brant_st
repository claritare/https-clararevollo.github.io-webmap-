<!DOCTYPE html>
<html>
<head>
  <title>Brant Street ZBA Proposal | Clara Revollo</title>

  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css"/>

  <style>
    body { margin:0; font-family: Arial, sans-serif; }

    #map { height: 100vh; }

    .panel {
      position: absolute;
      top: 20px;
      left: 20px;
      width: 340px;
      background: white;
      padding: 18px;
      border-radius: 10px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.25);
      z-index: 1000;
    }

    .panel h1 {
      font-size: 18px;
      margin: 0 0 5px 0;
    }

    .panel h2 {
      font-size: 13px;
      margin: 0 0 12px 0;
      color: #666;
    }

    .panel p {
      font-size: 13px;
      line-height: 1.5;
      margin-bottom: 10px;
    }

    .panel button {
      background: #8b5a2b;
      color: white;
      border: none;
      padding: 8px 12px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 12px;
    }

    .panel button:hover {
      background: #6e4522;
    }

    .legend {
      position: absolute;
      bottom: 20px;
      right: 20px;
      background: white;
      padding: 10px;
      border-radius: 8px;
      font-size: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    .legend div {
      margin-bottom: 4px;
    }
  </style>
</head>

<body>

<div id="map"></div>

<div class="panel">
  <h1>Brant Street ZBA Proposal</h1>
  <h2>Clara Revollo</h2>

  <p>
    This parcel represents a proposed redevelopment site located along Brant Street in downtown Burlington.
  </p>

  <p>
    A <strong>Zoning By-law Amendment (ZBA)</strong> is required to rezone the site from 
    <strong>DC-16 (Development Control)</strong> to 
    <strong>Downtown Core (DW)</strong>.
  </p>

  <p>
    The amendment will enable a <strong>mixed-use building</strong> and establish appropriate zoning standards for intensification.
  </p>

  <button onclick="zoomToSite()">Zoom to Site</button>
</div>

<div class="legend">
  <strong>Legend</strong>
  <div>🟤 Proposed Development Parcel</div>
</div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<script>
const proposedData = {
  "type":"FeatureCollection",
  "features":[
    {
      "type":"Feature",
      "geometry":{
        "type":"Polygon",
        "coordinates":[[
          [-79.80285384195629,43.32995022485604],
          [-79.80263926497759,43.32978243243733],
          [-79.80317034268543,43.3293648992679],
          [-79.80212964532696,43.32865469630703],
          [-79.80103530417297,43.32948976888639],
          [-79.80231740040787,43.33033263471011],
          [-79.80285384195629,43.32995022485604]
        ]]
      },
      "properties":{
        "Name":"Brant St Development",
        "Type":"Mixed-use",
        "Height":"20 storeys",
        "Status":"Proposed"
      }
    }
  ]
};

const map = L.map("map").setView([43.3295, -79.8021], 15);

L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png").addTo(map);

const proposedLayer = L.geoJSON(proposedData, {
  style: {
    color: "#8b5a2b",
    weight: 3,
    fillColor: "#c58b57",
    fillOpacity: 0.5
  },
  onEachFeature: (f, l) => {
    l.bindPopup(`
      <strong>${f.properties.Name}</strong><br>
      ${f.properties.Type}<br>
      ${f.properties.Height}<br>
      ${f.properties.Status}
    `);
  }
}).addTo(map);

function zoomToSite() {
  map.fitBounds(proposedLayer.getBounds(), { padding: [40, 40] });
}
</script>

</body>
</html>
