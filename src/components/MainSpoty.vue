<template>
  <main class="bg-dark">
    <div class="container">
      <div v-if="arrCovers == null" clasS="text-center text-white p-5">Loading..</div>
      <div v-else class="row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-5 d-flex align-items-stretch flex-wrap">
        <CoverCards
          v-for="card in arrCovers"
          :key="card.title"
          :character-data="card"
        />
      </div>
    </div>
  </main>
</template>

<script>

import CoverCards from './CoverCards.vue'
import axios from 'axios'

export default {
  name: 'MainSpoty',
  data () {
    return {
      arrCovers: null
    }
  },
  components: {
    CoverCards
  },
  created () {
    setTimeout(() => {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
          this.arrCovers = response.data.response
        })
    }, 2000)
  }
}
</script>

<style scoped lang="scss">
  main {
    height: 90vh;
  }
</style>
