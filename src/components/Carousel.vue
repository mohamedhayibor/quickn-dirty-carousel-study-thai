<template>
  <div style="height: 100%">
    <v-carousel
            height="100%"
            hide-delimiters
            show-arrows-on-hover
            @change="input"
    >
      <v-carousel-item
              v-for="(word, id) in words"
              :key="id"
      >
        <v-sheet
                :color="colors[id % 5]"
                height="100%"
                @click="flip = !flip"
        >
          <v-row
                  class="fill-height"
                  align="center"
                  justify="center"
          >
            <div class="display-3" v-if="flip">{{ word[0] }}</div>
            <div class="display-3" v-else>{{ word[1] }}</div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
    <div class="controls">
      <v-btn class="" @click="changeMode">f</v-btn>
    </div>
  </div>
</template>

<script>
  import axios from "axios";
  import { parse } from "papaparse";
  export default {
    async created () {
      const { data } = await axios.get("/data.csv");
      this.words  = parse(data).data.slice(1);
    },
    data () {
      return {
        flipped: false,
        flip: false,
        colors: [
          'indigo',
          'warning',
          'pink darken-2',
          'red lighten-1',
          'deep-purple accent-4',
        ],
        words: [],
      }
    },
    methods: {
      input() {
        this.flip = this.flipped;
      },
      changeMode() {
        this.flipped = !this.flipped;
        this.flip = !this.flip;
      }
    }
  }
</script>
<style>
  .controls {
    position: absolute;
    top: 10px;
    left: 10px;
  }
</style>
