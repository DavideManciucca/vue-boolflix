<template>
<div>
  <h1>Risultati ricerca</h1>
<div>
<ul v-for="film in listaFilm" :key="`${film.id}`">
  <li>{{film.title}}</li>
  <li>{{film.original_title}}</li>
  <li>{{film.vote_average}}</li>
</ul>
</div>

</div>
</template>

<script>


export default {
  name:'MainComp',
  props:{
    listaFilm:Array
  }

}
</script>


<style langh="scss" scoped>

</style>