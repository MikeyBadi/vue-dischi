<template>
  <select 
      v-model="genre"
      @change="$emit('selectGenre',genre)"
      id="genere">
        <option selected>Seleziona un genere</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
  </select>
</template>

<script>

export default {
  name:'mbSelect',
  data() {
    return {
      genre: "Seleziona un genere"
    };
  }

}
</script>

<style>

</style>