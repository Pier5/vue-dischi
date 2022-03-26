<template>
  <header class="bg-secondary d-flex align-items-center">
    <img class="h-75 ms-2" src="../assets/img/logo-small.svg"  alt="logo spotify">
    <SelectGenreBar @select="catchGenre" />
    <SelectAuthorBar @select="catchAuthor" />
  </header>
</template>

<script>

import SelectGenreBar from './SelectGenreBar.vue'
import SelectAuthorBar from './SelectAuthorBar.vue'

export default {
  name: 'HeaderSpoty',
  components: {
    SelectGenreBar,
    SelectAuthorBar
  },
  methods: {
    catchGenre (selectElement) {
      this.$emit('selectGenre', selectElement)
    },
    catchAuthor (selectAuthorElement) {
      this.$emit('selectAuthor', selectAuthorElement)
    }
  }
}
</script>

<style scoped lang="scss">
  header {
    height: 4rem;
  }
</style>
