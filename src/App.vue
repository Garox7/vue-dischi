<template>
<div>
  <HeaderPage @getFilterValue="filteValue"/>
  <MainPage :valueOfFilter="valueProps"/>
</div>
</template>

<script>
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';

export default {
  components: {
    HeaderPage,
    MainPage,
  },
  data() {
    return {
      valueProps: '',
    };
  },
  methods: {
    filteValue(newValue) {
      this.valueProps = newValue;

      console.log('Il valore è arrivato all\'app:', this.valueProps); // DEBUG
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-family: 'Lato', sans-serif;
}

body {
  background-color: rgb(33 44 58);
}
</style>
