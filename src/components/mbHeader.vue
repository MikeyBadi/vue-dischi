<template>
  <header class="d-flex justify-content-between">
    <img src="../assets/img/logo-small.svg" alt="">
    <div>
      <select v-model="genreToSearch" @change="$emit('startSearch', genreToSearch)">
        <option selected  value="">Seleziona un genere</option>
        <option 
        v-for="(genre, index) in genres"
        :key="`genre${index}`"
        :value="genre">{{genre}}</option>

      </select>
    </div>

  </header>
</template>

<script>



export default {
    name: "mbHeader",
  props:{
    genres: Array
  },
    data(){
      return{
        genreToSearch:''
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