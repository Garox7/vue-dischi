<template>
  <label for="search__album">Cerca in base al genere
    <select name="search__album" id="search__album"
      v-model="valueSelect"
      @change="$emit('getFilterValue', valueSelect)"
    >
      <option value="none">Seleziona un opzione</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </label>
</template>

<script>
export default {
  name: 'inputSearch',
  data() {
    return {
      valueSelect: 'none',
    };
  },
};
</script>

<style>

</style>
