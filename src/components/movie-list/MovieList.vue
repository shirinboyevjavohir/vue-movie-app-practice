<template>
  <div class="movie-list components-common-style">
    <ul class="list-group">
      <MovieListItem v-for="movie in movies" :movie="movie" />
    </ul>
  </div>
</template>
<script>
import MovieListItem from "../movie-list-item/MovieListItem.vue";
export default {
  components: {
    MovieListItem,
  },
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style scoped></style>
