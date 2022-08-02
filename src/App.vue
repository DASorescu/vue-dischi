<template>
  <div>
    <BaseHeader :generi="this.generi" @genre-change="setSelectedGenre"></BaseHeader>
    <TheMain @generi="getGer" :selected-genre="selectedGenre"></TheMain>
  </div>
</template>

<script>

import BaseHeader from './components/BaseHeader'
import TheMain from './components/TheMain'

export default {
  name: 'App',
  data() {
    return {
      generi: [],
      selectedGenre: '',
    }
  },
  components: {
    BaseHeader,
    TheMain,
  },
  methods: {
    getGer(generi) {
      this.generi = generi
    },
    setSelectedGenre(genre) {
      this.selectedGenre = genre;
    }
  },
}
</script>

<style lang="scss">
@import'./assets/scss/style.scss';
</style>
