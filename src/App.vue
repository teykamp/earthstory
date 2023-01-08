<template>
  <v-app>
    <TitleContent/>
    <MainContent/>
  </v-app>
</template>

<script>
import TitleContent from './components/TitleContent.vue'
import MainContent from './components/MainContent';

export default {
  name: 'App',

  components: {
    TitleContent,
    MainContent,

  },

  data: () => ({
    //
  }),
};
</script>
