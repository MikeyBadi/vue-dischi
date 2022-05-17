<template>
  <div class="spoty">
    <mbHeader/>
    <mbMain/>
  </div>
</template>

<script>

import mbHeader from './components/mbHeader.vue'
import mbMain from './components/mbMain.vue'

export default {
  name: 'App',
  components: {
    mbHeader,
    mbMain
  }
}
</script>

<style lang="scss">
@import '../src/assets/style/general';
@import './assets/style/vars';


</style>
