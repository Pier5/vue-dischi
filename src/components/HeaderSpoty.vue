<template>
  <header class="bg-secondary d-flex align-items-center">
    <img class="h-75 ms-2" src="../assets/img/logo-small.svg"  alt="">
    <SelectGenreBar @select="catchGenre" />
  </header>
</template>

<script>

import SelectGenreBar from './SelectGenreBar.vue'

export default {
  name: 'HeaderSpoty',
  components: {
    SelectGenreBar
  },
  methods: {
    catchGenre (selectElement) {
      this.$emit('selectGenre', selectElement)
    }
  }
}
</script>

<style scoped lang="scss">
  header {
    height: 4rem;
  }
</style>
