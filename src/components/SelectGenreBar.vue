<template>
  <select class="ms-auto p-1 me-4" name="search-genre" id="search-genre" v-model="strSelect" @change="$emit('select', strSelect)">
    <option value="">Cerca per Genere</option>
    <option v-for="element in filterArrOptions" :key="element" :value="element">{{ element }}</option>
  </select>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SelectGenreBar',
  data () {
    return {
      strSelect: '',
      arrCovers: [],
      arrOptions: []
    }
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        this.arrCovers = response.data.response
      })
  },
  computed: {
    filterArrOptions () {
      this.arrCovers.forEach((el) => {
        if (!this.arrOptions.includes(el.genre)) {
          this.arrOptions.push(el.genre)
        }
      })
      return this.arrOptions
    }
  }
}
</script>

<style>

</style>
