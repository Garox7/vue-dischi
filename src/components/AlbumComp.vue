<template>
  <div class="card-container">
    <img :src="poster" :alt="title">
    <h2>{{ title }}</h2>
    <p class="author">{{ author }}</p>
    <p class="year"> {{ year }}</p>
    <p>{{ genre }}</p>
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
    genre: String,
  },
};
</script>

<style lang="scss" scoped>
.card-container {
  background-color: rgb(49 58 69);
  color: white;
  text-align: center;
  padding: 1rem;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-content: center;

  img {
    max-width: 100%;
    aspect-ratio: 1/1;
    margin-bottom: .5rem;
    border-radius: 5px;
  }

  h2 {
    font-size: 18px;
    margin-bottom: 1rem;
  }

  .author {
    font-size: 14px;
    color: rgba(255, 255, 255, 0.6);
  }

  .year {
    font-size: 14px;
    color: rgba(255, 255, 255, 0.6);
  }
}
</style>
