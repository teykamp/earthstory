<template>
  <v-app>
    <TitleContent/>
    <MainContent/>
    <FooterContent/>
  </v-app>
</template>

<script>
import TitleContent from './components/TitleContent.vue'
import MainContent from './components/MainContent';
import FooterContent from './components/FooterContent.vue';

export default {
  name: 'App',

  components: {
    TitleContent,
    MainContent,
    FooterContent,
  },

  data: () => ({
    //
  }),
};
</script>
