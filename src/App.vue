<template>
  <div id="app">
    <HeaderSpoty @selectGenre="setStrSelect" />
    <MainSpoty :str-select="strSelect" />
  </div>
</template>

<script>

import HeaderSpoty from './components/HeaderSpoty.vue'
import MainSpoty from './components/MainSpoty.vue'

export default {
  name: 'App',
  components: {
    HeaderSpoty,
    MainSpoty
  },
  data () {
    return {
      strSelect: ''
    }
  },
  methods: {
    setStrSelect (selectElement) {
      this.strSelect = selectElement
    }
  }
}
</script>

<style lang="scss">
@import './assets/styles/style.scss';
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
