<template>
  <div class="spoty">
    <mbHeader @getGenreEvent ="filteredByGenre"/>
    <div class="d-flex justify-content-center">
      <mbMain/> 
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
      cardType: '',
      cardArtist: '',
    }
  },

  methods: {
    filteredByGenre(cardGenre){
      console.log('ascotatore 2');
      this.cardType = cardGenre;
    },

    filteredByArtist(artistString){
      console.log('ascoltatore 2 artist');
      this.cardArtist = artistString;
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
