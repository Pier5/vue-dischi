<template>
  <select class="ms-auto p-1 me-2" name="search-genre" id="search-genre" v-model="strSelect" @change="$emit('select', strSelect)">
    <option value="">All</option>
    <option value="rock">Rock</option>
    <option value="pop">Pop</option>
    <option value="jazz">Jazz</option>
    <option value="metal">Metal</option>
  </select>
</template>

<script>
export default {
  name: 'SelectGenreBar',
  data () {
    return {
      strSelect: ''
    }
  }
}
</script>

<style>

</style>
