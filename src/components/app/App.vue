<template>
  <div class="app font-monspace">
    <div class="content">
      <AppInfo
        :allMoviesCount="movies.length"
        :favouriteMoviesCount="movies.filter((c) => c.favourite).length"
      />
      <div class="search-panel components-common-style">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList :movies="movies" />
      <MovieAddItem @createMovie="createMovie" />
    </div>
  </div>
</template>

<script>
import AppInfo from "../app-info/AppInfo.vue";
import SearchPanel from "../search-panel/SearchPanel.vue";
import AppFilter from "../app-filter/AppFilter.vue";
import MovieList from "../movie-list/MovieList.vue";
import MovieAddItem from "../movie-add-item/MovieAddItem.vue";
export default {
  components: {
    AppInfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddItem,
  },
  // data
  data() {
    return {
      movies: [
        {
          name: "Osmaondagi bolalar",
          viewers: 234,
          favourite: false,
          like: true,
        },
        {
          name: "Spidermen",
          viewers: 899,
          favourite: true,
          like: true,
        },
        {
          name: "The Godfather",
          viewers: 944,
          favourite: true,
          like: false,
        },
      ],
    };
  },
  // Methods
  methods: {
    createMovie(item) {
      this.movies.push(item);
    },
  },
};
</script>

<style>
.app {
  width: 100vw;
  height: 100vh;
  color: #000;
}

.content {
  width: 1000px;
  min-height: 700px;
  background-color: #fff;
  margin: 0 auto;
  padding: 5rem 0;
}
</style>
