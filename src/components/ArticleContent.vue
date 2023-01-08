<template>
  <div>
   <v-card tile elevation="0" class="mb-8">
    <v-card tile elevation="0" class="d-flex justify-center mb-6">
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
   </v-card>

  </div>
</template>

<script>
export default {
  name: 'ArticleContent',
  props: {
    title: String,
    body: String,
    coordinates: Array, 
    imgPath: String,  // make list of images
  },
}
</script>

<style scoped>

</style>