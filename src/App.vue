<template>
  <div class="spoty">
    <mbHeader 
    @startSearch="startSearch"
    :genres="genres"/>
    <div class="d-flex justify-content-center">
      <mbMain 
      :genreToSearch="genreToSearch"
      @getGeneresList="getGeneresList"/> 
    </div>
    
  </div>
</template>

<script>
import mbHeader from "./components/mbHeader.vue";
import mbMain from "./components/mbMain.vue";



export default {
  name: 'App',
  components: {
    mbHeader,
    mbMain
  },

  data() {
    return {
      genreToSearch:'',
      genres: []
    }
  },

  methods: {
    startSearch(genreToSearch){
      this.genreToSearch = genreToSearch;
      console.log(genreToSearch);
    },
    getGeneresList(genres){
      this.genres = genres;
    }

  }
}
</script>

<style lang="scss">
@import '../src/assets/style/general';
@import './assets/style/vars';

.spoty{
  background-color: $bg;
}

</style>
