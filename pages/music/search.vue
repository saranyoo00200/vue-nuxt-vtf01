<template>
  <div>
    <h1>
      iTunes Music Search
    </h1>
    <v-text-field
      v-model="query"
      label="Regular"
    />
    <v-btn @click="searchMusics()">
      Search
    </v-btn>
    <v-divider class="mt-2 mb-2" />
    <div class="d-flex flex-wrap">
      <v-card
        v-for="music in results"
        :key="music.trackId"
        class="ma-5"
        max-width="344"
        outlined
        :to="{ name: 'pageInfo-id', params: { id: music } }"
      >
        <v-list-item three-line>
          <v-list-item-content>
            <div class="overline mb-4">
              {{ music.kind }}
            </div>
            <v-list-item-title class="headline mb-1">
              {{ music.trackName }}
            </v-list-item-title>
            <v-list-item-subtitle>Artist:{{ music.artistName }} Album :{{ music.collectionName }}</v-list-item-subtitle>
          </v-list-item-content>

          <img :src="music.artworkUrl60" alt="" :style="{width: '80px',marginTop:'10px'}">
        </v-list-item>
      </v-card>
    </div>
    </h1t>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      query: '',
      results: []
    }
  },
  methods: {
    searchMusics () {
      // eslint-disable-next-line no-template-curly-in-string
      const url = 'https://itunes.apple.com/search?term=' + this.query
      axios.get(url).then((res) => {
        // eslint-disable-next-line no-console
        console.log(res.data)
        this.results = res.data.results
      })
    }
  }

}
</script>

<style>

</style>
