<template>
  <div id="app">
    <div>
      <b-card
        overlay
        img-src="https://foriio.imgix.net/store/7e41bcf78775548f32ebb410ad96ba4a.png?ixlib=rb-3.1.1&w=1600&auto=format%2Ccompress&s=353e29118634936846070d894ef0543e"
        img-alt="Card Image"
        text-variant="white"
        title="Animetion info"
        sub-title="InsertAnimeName"
        img-height="350px"
      >
        <b-card-text></b-card-text>
      </b-card>
    </div>
    <Photo />
  </div>
</template>

<script>
import Photo from "./components/Photo.vue";

export default {
  name: "App",
  components: {
    Photo,
  },
};
</script>

<style>
#app {
  font-family: "Permanent Marker", cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #646464;
}
</style>
