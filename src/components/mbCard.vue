<template>
  <div class=" mb-card">
    <div class=" mb-imgCont">
      <img :src="songCard.poster" :alt="songCard.title">
    </div>
    <div class="mb-cardTxt">
      <h5>{{songCard.title}}</h5>
      <span>{{songCard.author}}</span>
      <span>{{songCard.year}}</span>
    </div>
  </div>
</template>

<script>

export default {
  name: 'mbCard',
  props:{
    songCard: Object
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars';
  .mb-card{
    padding: 10px;
    width: calc(100% / 6);
    background-color: $contouring;
    margin: 0 10px 30px;
    .mb-imgCont{
      width: 100%;
      img{
        width: 100%;
        margin-bottom: 10px;
      }
    }
    .mb-cardTxt{
      text-align: center;
      h5{
        color:$title-txt;
        font-size: 14px;
        text-transform: uppercase;
      }
      span{
        display: block;
        color: $song-name;
      }
    }
  }
</style>