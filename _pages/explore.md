---
layout: page
title: "Explore"
permalink: /explore/
---

# My Travels

<div id="map" style="width: 100%; height: 500px;"></div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css"/>

<script>
  // Initialize the map
  var map = L.map('map').setView([20, 0], 2); // World view

  // Add OpenStreetMap tiles
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  }).addTo(map);

  // Add pins for cities
  var cities = [
    {name: "Stanford, CA", coords: [37.4275, -122.1697]},
    {name: "Paris, France", coords: [48.8566, 2.3522]},
    {name: "Tokyo, Japan", coords: [35.6895, 139.6917]},
    // Add more cities here
  ];

  cities.forEach(function(city) {
    L.marker(city.coords).addTo(map)
      .bindPopup(city.name);
  });
</script>
