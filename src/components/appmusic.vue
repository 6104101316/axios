<template>
  <div>
     <!-- <b-themplate>
        <h4>Please type a song to plays.</h4>
      </b-themplate> -->
    <b-container fluid class="bv-example-row mb-4">
      <input type="text" v-model="keyword" />
     
      <b-button variant="dark" @click="searchData()">Search music (En)</b-button>
      <!-- {{resultData}} -->
    </b-container>
    <b-container fluid class="bv-example-row">
      <b-row align-h="around mr-4 ml-4">
        <b-card
          v-for="data in resultData"
          :key="data.trackId"
          :title="data.trackName"
          :img-src="data.artworkUrl60"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem"
          class="mb-2"
        > {{data.collectionCensoredName}}
          <audio controls>
            <source :src="data.previewUrl" type="audio/mpeg" />
          </audio>
          <b-button :href="data.trackViewUrl" variant="dark"
            >Go preview</b-button >
        </b-card>
      </b-row>
    </b-container>
  </div>
</template>


<script>
import Axios from "axios";
export default {
  data() {
    return {
      resultData: null,
      keyword: "",
    };
  },

  methods: {
    searchData() {
      console.log("searchData");
      Axios.get("https://itunes.apple.com/search?term=" + this.keyword + "")
      
        .then((response) => {
          this.resultData = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>


<style>
</style>