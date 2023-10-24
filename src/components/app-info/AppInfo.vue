<template>
  <div class="app-info components-common-style">
    <p class="fs-4 text-uppercase">Barcha kinolar soni: {{ allMoviesCount }}</p>
    <p class="fs-5 text-uppercase">
      Ko'rilgan kinolar soni: {{ favouriteMoviesCount }}
    </p>
  </div>
</template>

<script>
export default {
  props: {
    allMoviesCount: {
      type: Number,
      required: true,
    },
    favouriteMoviesCount: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style></style>
