<template>
  <header>
    <div class="logo">
      <img src="@/assets/logo.png" alt="Logo">
    </div>
    <div class="filter">
      <InputSearch @getFilterValue="getFilterValue" />
    </div>
  </header>
</template>

<script>
import InputSearch from '@/components/InputSearch.vue';

export default {
  components: {
    InputSearch,
  },
  name: 'HeaderPage',
  methods: {
    getFilterValue(value) {
      this.$emit('getFilterValue', value);

      console.log('valore trasmesso all\'Header:', value); // DEBUG
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: rgb(49 58 69);
  padding: .3rem;
  display: flex;

  .logo {
    flex: 0 0 auto;

    img {
      width: 40px;
    }
  }

  .filter {
    flex: 1 1 auto;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
