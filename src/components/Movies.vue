<template>
  <div class="movies">
    <input v-model="query" />
    <button class="btn btn-primary" @click="searchMovies(query)">Search</button>
    <div class="row">
      <div class="col-12">
        <movie
          v-for="(movieObj, index) in movies"
          :key="movieObj._id"
          :movieData="movieObj"
          :movieIndex="index"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Movie from "./Movie";

export default {
  name: "Movies",
  mounted() {
    this.$store.dispatch("setMovies");
  },
  data() {
    return {
      query: ""
    };
  },
  methods: {
    searchMovies(query) {
      this.$store.dispatch("searchMovies", query);
    }
  },
  computed: {
    movies() {
      return this.$store.state.movies;
    }
  },
  components: {
    Movie
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
