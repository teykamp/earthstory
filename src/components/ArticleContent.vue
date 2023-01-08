<template>
  <div>
   <v-card tile elevation="0" :color="bgColor" class="pa-6">
    <v-card tile elevation="0" class="d-flex justify-center mb-6" :color="bgColor">
      <v-img
      :src="require('../assets/articles/images/' + imgPath)"
      max-height="750"
      max-width="750"
      ></v-img>
    </v-card>
    <v-card-title 
    class="justify-center"
    >
      {{ title }}
    </v-card-title>
    <v-card-text 
    class="text-center"
    >
      {{ body }}
    </v-card-text>

    
    <v-card tile elevation="0" class="d-flex justify-center pb-6" :color="bgColor">
      <iframe
        :src="embedLink.toString()"
        width="50%" height="500vw" style="border:0;" allowfullscreen="" loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"></iframe>
    </v-card>



   </v-card>

  </div>
</template>

<script>
export default {
  name: 'ArticleContent',
  props: {
    title: String,
    body: String,
    location: Array, 
    imgPath: String,  // make list of images
    embedLink: String,
  },
  data() {
    return {
      bgColor: "grey lighten-3",
    }
  },
}
</script>

<style scoped>

</style>