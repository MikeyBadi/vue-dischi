<template>
  <header class="d-flex justify-content-between">
    <img src="../assets/img/logo-small.svg" alt="">
    <mbSelect
    @selectGenre="getCardForGenre"
    />
  </header>
</template>

<script>

import mbSelect from "./mbSelect.vue";


export default {
    name: "mbHeader",
    components: {
      mbSelect
      },

    data(){
      return{
        
      }
    },
   
    methods: {
        getCardForGenre(cardGenre){
          this.$emit('getGenreEvent', cardGenre);
        }
    },
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';
  header{
    padding: 10px 20px;
    background-color: $contouring;

    img{
      height: 40px;
      color:$spoty;
    }
  }
</style>