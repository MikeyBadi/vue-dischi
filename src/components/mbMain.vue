<template>
  <div class="stampCard d-flex flex-wrap justify-content-center"
  v-if="loading">
      <mbCard
      v-for="(song, index) in discFiltered" :key="`song-${index}`"
      :songCard="song"
      />
  </div>
  <loaderComp
  v-else/>
</template>

<script>
import axios from 'axios'
// ^ importare axios
import mbCard from './mbCard.vue'
import loaderComp from './loaderComp.vue'
export default {
  name:'cardCont',
  components: {
    mbCard,
    loaderComp
  },
  props:{
    genreToSearch: String
  },
  // v dare tutti i dati per la ricezione della API
  data() {
  return {
    url:'https://flynn.boolean.careers/exercises/api/array/music',
    songsArr:[],
    loading: false
  }
  // v fai partire la funzione appena apre la pagina
  },
  mounted() {
    setTimeout(()=>{this.getAPI()}, 2000)
  },
  // v crea la funzione che prende i dati dall'API
  methods: {
    getAPI(){
      axios.get(this.url)
      .then(r=>{
        this.songsArr = r.data.response;
        // console.log(r.data.response);
        const genres = []
        this.songsArr.forEach(song => {
          if(!genres.includes(song.genre)) genres.push(song.genre);
        });
        this.$emit('getGeneresList', genres)
        this.loading = true
      })
    }
  },
  computed:{
    discFiltered(){
      if(this.genreToSearch === ''){
        return this.songsArr
      }
      return this.songsArr.filter(song => song.genre === this.genreToSearch)
    }
  }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';

.stampCard{
  margin-top: 60px;
  width: 1000px;

}

</style>