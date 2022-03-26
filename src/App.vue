<template>
  <div id="app">
    <HeaderSpoty @selectGenre="setStrSelect" @selectAuthor="setStrAuthorSelect" />
    <MainSpoty :str-select="strSelect" :str-author-select="strAuthorSelect" />
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
      strSelect: '',
      strAuthorSelect: ''
    }
  },
  methods: {
    setStrSelect (selectElement) {
      this.strSelect = selectElement
    },
    setStrAuthorSelect (selectAuthorElement) {
      this.strAuthorSelect = selectAuthorElement
    }
  }
}
</script>

<style lang="scss">
@import './assets/styles/style.scss';
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
