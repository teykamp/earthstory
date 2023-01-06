<template>
  <v-app>
    <MainContent/>
  </v-app>
</template>

<script>
import MainContent from './components/MainContent';

export default {
  name: 'App',

  components: {
    MainContent,
  },

  data: () => ({
    //
  }),
};
</script>
