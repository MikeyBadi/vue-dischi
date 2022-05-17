<template>
  <header class="d-flex justify-content-between">
    <img src="../assets/img/logo-small.svg" alt="">
    <select name="genere" id="" placeholder="Seleziona un genere">
      <option value="all">Seleziona un genere</option>
      <option value="rock">Rock</option>
      <option value="metal">Metal</option>
    </select>
  </header>
</template>

<script>
export default {
name: 'mbHeader'
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