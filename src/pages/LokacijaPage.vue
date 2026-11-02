<template>
  <q-page padding>
    <h4 class="text-h4">Lokacija knjižnice</h4>

    <p>
      Na karti možete pogledati lokaciju Gradske knjižnice Rijeka.
    </p>

    <div id="map" style="height: 500px;"></div>
  </q-page>
</template>

<script setup>
import { onMounted } from 'vue'
import * as L from 'leaflet'
import 'leaflet/dist/leaflet.css'

onMounted(() => {
  const map = L.map('map').setView([45.3312, 14.4322], 13)

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; OpenStreetMap contributors'
  }).addTo(map)
})
</script>