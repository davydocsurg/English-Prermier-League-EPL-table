<template>
  <div>
  <router-link to="/" class="ho">Home</router-link>
  <b-row>
    <b-col cols="12">
      <h2>
        Team  Map
      </h2>
      <GoogleMapLoader
        :mapConfig="mapConfig"
        apiKey="API KEY"
      >
      </GoogleMapLoader>
    </b-col>
  </b-row>
  </div>
</template>

<script>
import GoogleMapLoader from "./GoogleMapLoader";

export default {
  components: {
    GoogleMapLoader
  },

  computed: {
    mapConfig () {
      return {
        mapSettings: {
          enableHighAccuracy: true,
          timeout: 5000,
          maximumAge: 0
        },
        zoom: 15,
        center: { lat: parseInt(this.$route.params.lat, 0), lng: parseInt(this.$route.params.lng, 0) }
      }
    },
  }
};
</script>

<style lang="css">
  .ho {
    font-weight: bold;
    color: green !important;
  }
</style>
