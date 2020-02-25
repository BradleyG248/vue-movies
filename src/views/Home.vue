<template>
  <div class="home container">
    <div class="row">
      <div class="col-6">
        <h1>Find a movie</h1>
        <movies />
      </div>
      <div class="col-6">
        <h1>Movie details</h1>
        <active-movie :movieData="activeMovie" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Movie from "@/components/Movie.vue";
import Movies from "@/components/Movies.vue";
import ActiveMovie from "@/components/ActiveMovie.vue";

export default {
  name: "Home",
  components: {
    Movies,
    ActiveMovie
  },
  computed: {
    activeMovie() {
      return this.$store.state.activeMovie;
    }
  }
};
</script>
