<template>
  <div>
    <div style="height: 10%; overflow: auto;">
      <h3>Set Bounds</h3>
      Marker is placed at {{ marker.lat }}, {{ marker.lng }}, bounds are {{ bounds }}
      <br>
    </div>
    <l-map
      :zoom="zoom"
      :center="center"
      :bounds="bounds"
      :max-bounds="maxBounds"
      style="height: 90%">
      <l-tile-layer
        :url="url"
        :attribution="attribution"/>
      <l-marker :lat-lng="marker"/>
    </l-map>
  </div>
</template>

<script>
import { LMap, LTileLayer, LMarker } from 'vue2-leaflet';

export default {
  name: 'SetBounds',
  components: {
    LMap,
    LTileLayer,
    LMarker
  },
  data () {
    return {
      zoom: 13,
      center: [0, 0],
      bounds: L.latLngBounds([[40.70081290280357, -74.26963806152345], [40.82991732677597, -74.08716201782228]]),
      maxBounds: L.latLngBounds([[40.70081290280357, -74.26963806152345], [40.82991732677597, -74.08716201782228]]),
      url: 'http://{s}.tile.osm.org/{z}/{x}/{y}.png',
      attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      marker: L.latLng(47.413220, -1.219482)
    };
  }
};
</script>
