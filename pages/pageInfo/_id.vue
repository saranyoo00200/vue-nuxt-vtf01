<template>
  <div class="mar">
    <v-card
      class="mx-auto"
      max-width="400"
    >
      <v-img
        class="white--text align-end"
        height="200px"
        :src="this.$route.params.id.artworkUrl60"
      >
        <v-card-title>{{ this.$route.params.id.artistName }}</v-card-title>
      </v-img>

      <v-card-subtitle class="pb-0">
        {{ this.$route.params.id.artistName }}
      </v-card-subtitle>

      <v-card-text class="text--primary">
        <div>Artist : {{ this.$route.params.id.artistName }}</div>

        <div>Album : {{ this.$route.params.id.collectionName }}</div>

        <div>Track Number : {{ this.$route.params.id.trackNumber }}</div>

        <div>Genre : {{ this.$route.params.id.primaryGenreName }}</div>

        <div>Release Date : {{ this.$route.params.id.releaseDate }}</div>

        <div>Full Album price : {{ this.$route.params.id.collectionPrice }} US</div>
      </v-card-text>

      <v-card-actions>
        <v-btn
          :href="this.$route.params.id.trackViewUrl"
          target="_blank"
          color="orange"
          text
        >
          View On Apple Music
        </v-btn>
      </v-card-actions>
      <v-card-text>
        <audio controls>
          <source :src="this.$route.params.id.previewUrl" type="audio/mpeg">
        </audio>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
}
</script>

<style>
.mar{
  margin-top: 15vh;
}
</style>
