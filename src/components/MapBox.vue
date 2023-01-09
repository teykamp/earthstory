<template>
  <l-map 
    style="height: 550px; width: 550px; background: #212121; cursor:default;" 
    :zoom="zoom" 
    :center="center" 
    :options="{ zoomControl: false, attributionControl: false, scrollWheelZoom: false, dragging: false, doubleClickZoom: false, boxZoom: false, keyboard: false }"
    
  >
    <l-geo-json :geojson="geojson" style="cursor:default;"></l-geo-json>
    <div v-for="latLong in markerLatLongList" :key="latLong[0]">
      <l-circle-marker
        :lat-lng="latLong"
        :color="markerColor"
        :fillOpacity="1"
        :fillColor="markerColor"
        :radius="radius"
      ></l-circle-marker>
    </div>
  </l-map>
</template>

<script>
import { LMap, LGeoJson, LCircleMarker } from 'vue2-leaflet';
import mapData from '../assets/mapData.json'
import latLongList from '../assets/articles/text/summaryCoordinates.json'


export default {
  components: {
    LMap,
    LGeoJson,
    LCircleMarker,
  },
  data() {
    return {
      zoom: 1,
      center: [47.313220, -1.319482],
      zoomControl: false,
      geojson: mapData,
      markerLatLongList: latLongList.coordinatesList,
      markerColor: 'red',
      radius: 4,
    };
  },
}
</script>
