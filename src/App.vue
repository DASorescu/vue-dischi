<template>
  <div>
    <BaseHeader></BaseHeader>
    <TheMain></TheMain>
  </div>
</template>

<script>

import BaseHeader from './components/BaseHeader'
import TheMain from './components/TheMain'

export default {
  name: 'App',
  components: {
    BaseHeader,
    TheMain,
  }
}
</script>

<style lang="scss">
@import'./assets/scss/style.scss';
</style>
