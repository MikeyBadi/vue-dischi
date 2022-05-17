<template>
  <main class="d-flex flex-wrap justify-content-center">
      <cardCont/>
  </main>
</template>

<script>

import cardCont from './cardCont.vue'
export default {
  name:'mbMain',
  components: {
    cardCont
  },
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';
main{
  background-color: $bg;
  height: 100vh;
}

</style>