<template>
  <main class="bg-dark">
    <div class="container">
      <div class="row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-5 d-flex align-items-stretch flex-wrap">
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
      arrCovers: []
    }
  },
  components: {
    CoverCards
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        this.arrCovers = response.data.response
        console.log(response.data.response)
      })
  }
}
</script>

<style scoped lang="scss">
  main {
    height: 90vh;
  }
</style>
