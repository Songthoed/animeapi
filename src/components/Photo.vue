<template>
  <div id="back">
    <br />
    <div class="row">
      <div class="col-1"></div>
      <div class="col-9">
        <b-form-input v-model="search" placeholder="Enter your name"></b-form-input>
      </div>
      <div class="col-1">
        <b-button variant="dark" @click="searchData()">Search</b-button>
      </div>
      <div class="col-1"></div>
    </div>
    <br />
    <div>
      <b-card-group group columns>
        <b-card
          no-body
          class="overflow-hidden"
          style="max-height: 540px;"
          v-for="anime in animelist"
          :key="anime.mal_id"
        >
          <b-row no-gutters>
            <b-col md="6">
              <b-card-img :src="anime.image_url" alt="Image" class="rounded-0" height="100%"></b-card-img>
            </b-col>
            <b-col md="6">
              <b-card-body :title="anime.title" body-bg-variant="dark" height="100%">
                <b-card-text>
                  Episodes : {{anime.episodes}}
                  <br />
                  Score : {{anime.score}}
                  <br />
                  Rated : {{anime.rated}}
                  <br />
                  {{anime.synopsis}}
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </b-card-group>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      animelist: null,
      search: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get("https://api.jikan.moe/v3/search/anime?q=" + this.search)
        .then((response) => {
          this.animelist = response.data.results.slice(0, 25);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
#back {
  background-size: cover;
  background-image: url(https://i.imgur.com/ybechRM.png);
  height: 500px;
}
</style>