<template>
  <div class="d-flex justify-content-center pt-2">
    <div class="cards text-center">
      <img class="w-100" :src="CharacterData.poster" :alt="CharacterData.title">
      <h2 class="text-white fs-5 p-2">{{ CharacterData.title }}</h2>
      <h3 class="fs-5 pt-1">{{ CharacterData.author }}</h3>
      <h4 class="fs-5">{{ CharacterData.year }}</h4>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CoverCards',
  props: {
    CharacterData: Object
  }
}
</script>

<style scoped lang="scss">
  .cards {
    width: 150px;
    background-color: gray
  }
</style>
