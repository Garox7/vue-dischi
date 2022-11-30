<template>
  <div class="main-container">
    <AlbumComp v-for="album in arrAlbumFilter"
      :key="album.name"
      :poster="album.poster"
      :title="album.title"
      :author="album.author"
      :year="album.year"
      :genre="album.genre"
      class="album-card"
    />
  </div>
</template>

<script>
import axios from 'axios';
import AlbumComp from '@/components/AlbumComp.vue';

export default {
  name: 'MainPage',
  components: {
    AlbumComp,
  },
  props: {
    genreFilter: String,
  },
  data() {
    return {
      arrAlbum: null,
      urlAPi: 'https://flynn.boolean.careers/exercises/api/array/music',
    };
  },
  created() {
    axios.get(this.urlAPi)
      .then((axiosResponse) => {
        this.arrAlbum = axiosResponse.data.response;

        console.log('Album:', this.arrAlbum); // DEBUG
      });
  },
  computed: {
    arrGenres() {
      const arrGenres = [];
      if (this.arrAlbum) {
        this.arrAlbum.forEach((objAlbum) => {
          if (!arrGenres.includes(objAlbum.genre)) {
            arrGenres.push(objAlbum.genre);
          }
        });
      }
      return arrGenres;
    },
    arrAlbumFilter() {
      if (this.genreFilter === 'all') {
        return this.arrAlbum;
      }
      return this.arrAlbum.filter((objAlbum) => objAlbum.genre === this.genreFilter);
    },
  },
  watch: {
    arrGenres(newValue) {
      this.$emit('genresReady', newValue);

      console.log('Array dei generi:', newValue); // DEBUG
    },
  },
};
</script>

<style lang="scss" scoped>
.main-container {
  max-width: 1000px;
  margin: 2rem auto 0 auto;
  padding: 1rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;

  .album-card {
    flex: 1 1 calc(100% / 5 - 2rem);
    max-width: 20%;
  }
}

@media screen and (max-width: 768px) {
  .main-container .album-card {
    flex: 1 1 calc(100% / 2 - 2rem);
    max-width: 50%;
  }
}
</style>
