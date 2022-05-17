<template>
  <div class="stampCard d-flex flex-wrap justify-content-center"
  v-if="loading">
      <mbCard
      v-for="(song, index) in songsArr" :key="`song-${index}`"
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
        console.log(r.data.response);
        this.loading = true
      })
    }
  },
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';

.stampCard{
  margin-top: 60px;
  width: 1000px;

}

</style>