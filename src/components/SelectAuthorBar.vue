<template>
  <select class="p-1 me-2" name="search-genre" id="search-genre" v-model="strAuthorSelect" @change="$emit('select', strAuthorSelect)">
    <option value="">Cerca per Artista</option>
    <option v-for="element in filterArrOptions" :key="element" :value="element">{{ element }}</option>
  </select>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SelectAuthorBar',
  data () {
    return {
      strAuthorSelect: '',
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
        if (!this.arrOptions.includes(el.author)) {
          this.arrOptions.push(el.author)
        }
      })
      return this.arrOptions
    }
  }
}
</script>

<style>

</style>
