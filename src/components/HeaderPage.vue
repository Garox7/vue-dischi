<template>
  <header>
    <div class="logo">
      <img src="@/assets/logo.png" alt="Logo">
    </div>
    <div class="filter">
      <label for="search__album">
        <select
        id="search__album"
        v-model="newOption"
        @change="changeOption"
        >
          <option value="all">
            Tutti i generi
          </option>

          <option
          v-for="option in genreOptions"
          :key="option"
          :value="option"
          >
          {{ option }}
        </option>
        </select>
      </label>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderPage',
  props: {
    genreOptions: Array,
  },
  data() {
    return {
      newOption: 'all',
    };
  },
  methods: {
    changeOption() {
      this.$emit('changeOption', this.newOption);
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

    select {
      background-color: rgb(33 44 58);
      color: white;
      border: 1px solid rgb(49 58 69);
      border-radius: 5px;
      height: 1.5rem;
      width: 150px;

      &:focus-visible {
        border: 1px solid white;
        outline: none;
      }
    }
  }
}
</style>
