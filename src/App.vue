<template>
  <v-app>
    <v-content>
      <Carousel/>
    </v-content>
  </v-app>
</template>

<script>
import Carousel from './components/Carousel';

export default {
  name: 'App',
  components: {
    Carousel,
  },
  data: () => ({
    //
  }),
};
</script>
