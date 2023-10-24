<template>
  <li
    class="list-group-item d-flex justify-content-between"
    :class="[{ favourite: movie.favourite }, { like: movie.like }]"
  >
    <span class="list-group-item-label">{{ movie.name }}</span>
    <input type="numer" class="list-group-item-input" :value="movie.viewers" />
    <div
      class="list-group-item-icons d-flex justify-content-center aligin-items-center gap-2"
    >
      <button type="button" class="btn-cookie btn-sm">
        <i class="fa fa-cookie"></i>
      </button>
      <button type="button" class="btn-trash btn-sm">
        <i class="fa-sharp fa-solid fa-trash"></i>
      </button>
      <button type="button" class="btn-star btn-sm">
        <i class="fa-sharp fa-solid fa-star"></i>
      </button>
    </div>
  </li>
</template>
<script>
export default {
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
};
</script>
<style scoped>
.list-group-item {
  padding: 15px 20px;
  border: none;
  border-bottom: 2px solid #3d5a80;
}

.list-group-item:last-child {
  border-bottom: none;
}

.list-group-item span {
  line-height: 35px;
  font-size: 20px;
  cursor: pointer;
  width: 500px;
  font-weight: 500;
}

.list-group-item input {
  line-height: 35px;
  font-size: 20px;
  text-align: center;
  border: none;
  outline: none;
}

.list-group-item button {
  width: 35px;
  height: 35px;
  font-size: 20px;
  margin: 3px;
  border: none;
  cursor: pointer;
  background-color: #fff;
}

.list-group-item .btn-cookie {
  color: #e09f3e;
}

.list-group-item .btn-trash {
  color: #e5383b;
}

.list-group-item .btn-star {
  color: #ffd700;
  transition: 0.3s all;
  transform: translateX(30px);
  opacity: 0;
}

.list-group-item.like .btn-star {
  opacity: 1;
  transform: translateX(0);
}

.list-group-item.favourite .list-group-item-label,
.list-group-item.favourite .list-group-item-input {
  color: #e09f3e;
}
</style>
