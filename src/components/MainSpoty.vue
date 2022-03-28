<template>
  <main>
    <div class="container">
      <div v-if="arrCovers == null" class="text-center text-white p-5">
        <LoadingPage />
      </div>
      <div v-else-if="selectOption == ''" class="pt-5">
        <span class="text-white text-uppercase">Nessun risultato trovato..</span>
      </div>
      <div v-else class="row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 d-flex align-items-stretch flex-wrap">
        <CoverCards
          v-for="card in selectOption"
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
  props: {
    StrSelect: String,
    strAuthorSelect: String
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
  },
  computed: {
    selectOption () {
      return this.arrCovers.filter((el) => {
        return el.genre
          .includes(this.StrSelect) &&
            el.author
              .includes(this.strAuthorSelect)
      })
    }
  }
}
</script>

<style scoped lang="scss">
</style>
