<template>
  <div class="container pt-5 px-4 px-sm-2">
    <div class="row justify-content-center">
      <AlbumComp v-for="album in arrAlbum"
        :key="album.name"
        :poster="album.poster"
        :title="album.title"
        :author="album.author"
        :year="album.year"
        class="col-6 col-sm-4 col-md-3"
      />
    </div>
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
  data() {
    return {
      arrAlbum: null,
      urlAPi: 'https://flynn.boolean.careers/exercises/api/array/music',
    };
  },
  created() {
    axios.get(this.urlAPi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrAlbum = axiosResponse.data.response;
        console.log(this.arrAlbum);
      });
  },
};
</script>

<style lang="scss" scoped>

</style>
