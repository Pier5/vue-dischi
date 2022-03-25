<template>
  <main>
    <div class="container">
      <div v-if="arrCovers == null" clasS="text-center text-white p-5">
        <LoadingPage />
      </div>
      <div v-else class="row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-5 d-flex align-items-stretch flex-wrap">
        <CoverCards
          v-for="card in selectGenre()"
          :key="card.title"
          :character-data="card"
        />
      </div>
    </div>
  </main>
</template>

<script>

import CoverCards from './CoverCards.vue'
import LoadingPage from './LoadingPage.vue'
import axios from 'axios'

export default {
  name: 'MainSpoty',
  data () {
    return {
      arrCovers: null
    }
  },
  methods: {
    selectGenre () {
      return this.arrCovers.filter((el) => {
        return el.genre.toLowerCase()
          .includes(this.StrSelect.toLowerCase())
      })
    }
  },
  props: {
    StrSelect: String
  },
  components: {
    CoverCards,
    LoadingPage
  },
  created () {
    setTimeout(() => {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
          this.arrCovers = response.data.response
        })
        .catch(() => {
          const error = document.createElement('div')
          error.style.color = 'white'
          const container = document.querySelector('.container')
          error.innerHTML = 'File non trovato, prova a ricaricare la pagina..'
          container.append(error)
        })
    }, 2000)
  }
}
</script>

<style scoped lang="scss">
</style>
