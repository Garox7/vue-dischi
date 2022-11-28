<template>
  <div class="album text-center text-light">
    <img
      :src="poster"
      :alt="title"
      class="img-fluid"
    >
    <h2 class="fs-6 mb-1">{{ title }}</h2>
    <p class="fs-6 mb-1">{{ author }}</p>
    <p class="fs-6"> {{ year }}</p>
  </div>
</template>

<script>
export default {
  name: 'AlbumComp',
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
.album {
  background-color: rgb(49 58 69);

  img {
    width: 150px;
    height: 150px;
  }
}
</style>
