<template>
  <!-- No need for this: hide-delimiter-background -->
  <v-carousel
    cycle
    height="100%"
    hide-delimiters
    show-arrows-on-hover
  >
    <v-carousel-item
      v-for="(word, id) in words"
      :key="id"
    >
      <v-sheet
        :color="colors[id % 5]"
        height="100%"
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="display-3">{{ word.eng }} | {{ word.thai }}</div>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>

</template>

<script>
  export default {
    data () {
      return {
        colors: [
          'indigo',
          'warning',
          'pink darken-2',
          'red lighten-1',
          'deep-purple accent-4',
        ],
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
          'Fifth',
        ],
        words: [{
                  "eng": "beautiful",
                  "thai": "sǔay"
                },
                {
                  "eng": "bored",
                  "thai": "bùa"
                },
                {
                  "eng": "cold",
                  "thai": "nǎaw"
                },
                {
                  "eng": "come",
                  "thai": "ma"
                },
                {
                  "eng": "difficult",
                  "thai": "yâak"
                },
                {
                  "eng": "doctor",
                  "thai": "mǒo"
                },
                {
                  "eng": "easy",
                  "thai": "ngâay"
                },
                {
                  "eng": "eat",
                  "thai": "kin"
                },
                {
                  "eng": "few, little",
                  "thai": "nóoy"
                },
                {
                  "eng": "full (finished eating)",
                  "thai": "ìm"
                },
                {
                  "eng": "hot",
                  "thai": "róon"
                },
                {
                  "eng": "hundred",
                  "thai": "róoy"
                },
                {
                  "eng": "hungry",
                  "thai": "hǐw"
                },
                {
                  "eng": "much, many, very",
                  "thai": "mâak"
                },
                {
                  "eng": "near",
                  "thai": "klâi"
                },
                {
                  "eng": "new",
                  "thai": "mài"
                },
                {
                  "eng": "no, not",
                  "thai": "mâi"
                },
                {
                  "eng": "often",
                  "thai": "bòy"
                },
                {
                  "eng": "tired",
                  "thai": "nùay"
                },
                {
                  "eng": "to do / to make",
                  "thai": "tham"
                },
                {
                  "eng": "to go",
                  "thai": "pai"
                },
                {
                  "eng": "to have",
                  "thai": "mii"
                },
                {
                  "eng": "to look for, to seek",
                  "thai": "hǎa"
                },
                {
                  "eng": "to love",
                  "thai": "rák"
                },
                {
                  "eng": "water",
                  "thai": "nám"
                },
                {
                  "eng": "where",
                  "thai": "thîinǎi"
                }]
      }
    },
  }
</script>