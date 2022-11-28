<template>
<div>
  <HeaderPage></HeaderPage>
  <MainPage></MainPage>
</div>
</template>

<script>
import HeaderPage from '@/components/HeaderPage.vue';
import mainPage from '@/components/MainPage.vue';

export default {
  components: {
    HeaderPage,
    mainPage,
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

html {
  font-family: 'Lato', sans-serif;
}
</style>
