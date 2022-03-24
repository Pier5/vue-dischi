<template>
  <div id="app">
    <HeaderSpoty />
    <MainSpoty />
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
  }
}
</script>

<style lang="scss">
@import './assets/styles/style.scss';
</style>
