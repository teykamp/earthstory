<template>
  <div>
    <v-card v-for="t in text" :key="t.id" tile elevation="0">
      <ArticleContent 
        :title="t.title"
        :subtitle="t.subtitle"
        :body="t.body"
        :location="t.location"
        :imgPath="t.imgPath"
        :embedLink="t.mapEmbed"
      />
      <v-divider color="gray"></v-divider>
    </v-card>
    <v-card 
      class="d-flex justify-center" 
      color="grey darken-3"
      tile
    >
      <v-tooltip top>
        <template v-slot:activator="{ on, attrs }">
          <v-btn 
            class="ma-16" 
            fab 
            dark 
            small 
            color="primary" 
            @click="scrollToTop()"
            v-bind="attrs"
            v-on="on"
          >
            <v-icon dark>
              mdi-chevron-double-up
            </v-icon>
          </v-btn>
        </template>
        <span>Return To Top</span>
      </v-tooltip>
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
    // this.importImg(require.context('../assets/articles/images', true, /\.png$/));
    this.importText(require.context('../assets/articles/text', true, /\.json$/));
  },

  methods: {
    // importImg(r) {
    //   r.keys().forEach(key => (this.images.push({ pathLong: r(key), pathShort: key })));
    // },
    importText(r) {
      r.keys().forEach(key => (this.text.push(r(key))));
    },
    scrollToTop() {
      window.scrollTo({ top: window.innerHeight, behavior: "smooth" });
    },
  }
}
</script>