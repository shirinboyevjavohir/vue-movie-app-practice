<template>
  <div class="movie-add components-common-style">
    <h3>Yangi kino qo'shish</h3>
    <form action="" class="add-form d-flex gap-3" @submit.prevent>
      <input
        type="text"
        class="form-control new-movie-label"
        placeholder="Qnday kino?"
        :value="name"
        v-on:input="name = $event.target.value"
      />
      <input
        type="number"
        class="form-control new-movie-label"
        placeholder="Necha maratoba ko'rilgan?"
        :value="viewers"
        v-on:input="viewers = $event.target.value"
      />

      <button class="btn btn-outline-dark" type="submit" v-on:click="addMovie">
        Qo'shish
      </button>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      viewers: "",
    };
  },
  methods: {
    addMovie() {
      const newMovie = {
        name: this.name,
        viewers: this.viewers,
        favourite: false,
        like: false,
      };
      this.$emit("createMovie", newMovie);
      this.name = "";
      this.viewers = "";
    },
  },
};
</script>
<style></style>
