<template>
  <div>
    <v-card
    dark 
    height="100vh" 
    color="grey darken-4" 
    tile
    class="pt-16"
    >
      <v-container class="pt-16">
        <v-row>
          <v-col class="d-flex align-center justify-center pl-16">
            <v-hover 
            v-slot="{ hover }"
            >
              <div 
              class="text-h1"
              :class="hover ? 'text-decoration-underline' : ''"
              style="cursor:default"
              >Earthstory</div>
            </v-hover>
          </v-col>
          <v-col class="pr-16">
            <MapBox/>
          </v-col>
        </v-row>
        <v-row class="justify-center mt-16" height="80vh" >
          <v-btn 
          class="mt-16" 
          fab 
          dark 
          small 
          color="primary"
          @click="scrollDownFromTop()">
            <v-icon dark>
            mdi-chevron-double-down
            </v-icon>
          </v-btn>
        </v-row>
      </v-container>
    </v-card>
  </div>
</template>

<script>
import MapBox from './MapBox.vue'
export default {
  name: 'TitleContent',
  components: {
    MapBox,
  },

  props : {
    coordinates: Array,
  },

  methods: {
    scrollDownFromTop() {
      window.scrollTo({ top: window.innerHeight, behavior: "smooth" });
    },
  }
}
</script>

<style scoped>

</style>
