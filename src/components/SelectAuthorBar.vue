<template>
  <select class="p-1 me-2" name="search-genre" id="search-genre" v-model="strAuthorSelect" @change="$emit('select', strAuthorSelect)">
    <option value="">Seleziona un Artista</option>
    <option value="bon jovi">Bon Jovi</option>
    <option value="queen">Queen</option>
    <option value="sting">Sting</option>
    <option value="steve gadd band">Steve Gadd Band</option>
    <option value="iron maiden">Iron Maiden</option>
    <option value="eric clapton">Eric Clapton</option>
    <option value="deep purple">Deep Purple</option>
    <option value="metallica">Metallica</option>
    <option value="dave weckl">Dave Weckl</option>
    <option value="michael jacjson">Michael Jacjson</option>
  </select>
</template>

<script>
export default {
  name: 'SelectAuthorBar',
  data () {
    return {
      strAuthorSelect: ''
    }
  }
}
</script>

<style>

</style>
