<template>
  <div>
    <BaseHeader :generi="this.generi"></BaseHeader>
    <TheMain @generi="getGer"></TheMain>
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
    }
  },
  components: {
    BaseHeader,
    TheMain,
  },
  methods: {
    getGer(generi) {
      this.generi = generi
    }
  }
}
</script>

<style lang="scss">
@import'./assets/scss/style.scss';
</style>
