<template>
  <div class="movie">
    <h5>{{movieData.title}}</h5>
    <img :src="this.pic + movieData.poster_path" @click="setActive" />
  </div>
</template>

<script>
import ActiveMovie from "./ActiveMovie";
export default {
  name: "Movie",
  props: ["movieData", "movieIndex"],
  methods: {
    setActive() {
      this.$store.dispatch("setActiveMovie", this.movieData);
    }
  },
  data() {
    return {
      pic: "https://image.tmdb.org/t/p/w200"
    };
  }
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
img {
  cursor: pointer;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
