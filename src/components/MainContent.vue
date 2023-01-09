<template>
  <div>
    <v-card v-for="t in text" :key="t.id">
      <ArticleContent 
        :title="t.title"
        :subtitle="t.subtitle"
        :body="t.body"
        :location="t.location"
        :imgPath="t.imgPath"
        :embedLink="t.mapEmbed"
      />
      <v-divider></v-divider>
    </v-card>
  </div>
</template>

<script>
import ArticleContent from './ArticleContent.vue'

export default {
  name: 'MainContent',
  components: {
    ArticleContent,
  },

  data() {
    return {
      images: [],
      text: [],
    }
  },

  mounted() {
    this.importImg(require.context('../assets/articles/images', true, /\.png$/));
    this.importText(require.context('../assets/articles/text', true, /\.json$/));
  },

  methods: {
    importImg(r) {
      r.keys().forEach(key => (this.images.push({ pathLong: r(key), pathShort: key })));
    },
    importText(r) {
      r.keys().forEach(key => (this.text.push(r(key))));
    },
  }
}
</script>