<template>
    <div id="app">
    <l-map
      :zoom="zoom"
      :center="center">
      <l-tile-layer
        :url="url"
        :attribution="attribution"/>
      <l-marker :lat-lng="marker">
      </l-marker>
    </l-map>
  </div>
</template>

<script>
import {LMap, LTileLayer, LMarker} from 'vue2-leaflet'
import L from 'leaflet'
export default {
  name: 'app',
  components:{ LMap, LTileLayer, LMarker },
  data() {
    return {
      zoom:13,
      center: L.latLng(1.3521, 103.8198),
      url:'https://cartodb-basemaps-{s}.global.ssl.fastly.net/rastertiles/voyager/{z}/{x}/{y}.png',
      attribution:'&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      marker: L.latLng(1.3521, 103.8198),
    }
  }
}
</script>

<style>
html, body, #app {
  height: 100%;
  margin: 0;
}
</style>
