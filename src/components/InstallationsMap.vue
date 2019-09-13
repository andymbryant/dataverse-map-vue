<template>
  <GoogleMapLoader
    :mapConfig="mapConfig"
    apiKey = "AIzaSyDBRKkuqhWPUIlZAHYCvzzgepn1ZOyBnBs"
  >
    <template slot-scope="{ google, map }">
      <GoogleMapMarker
        v-for="marker in markers"
        :key="marker.id"
        :marker="marker"
        :google="google"
        :map="map"
      />
    </template>
  </GoogleMapLoader>
</template>

<script>
import GoogleMapLoader from './GoogleMapLoader'
import GoogleMapMarker from './GoogleMapMarker'
import { mapSettings } from '@/constants/mapSettings'

import { installations } from '@/data/installations'

export default {
  components: {
    GoogleMapLoader,
    GoogleMapMarker
  },
  data: () => ({
    markers: installations
  }),
  computed: {
    mapConfig () {
      return {
        ...mapSettings,
        center: this.mapCenter
      }
    },
    mapCenter () {
      return { "lat": 42.380098, "lng": -71.116629 }
    }
  },
}
</script>