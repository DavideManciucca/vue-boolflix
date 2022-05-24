<template>
<div class="container">
  <div>
    <h1>{{titleCards}}</h1>
  </div>
  
  <div class="card-wrapper">
  <CardComp
   v-for="film in listaFilm" :key="film.id" :cardData="film"
   />


<!-- <div>
<ul v-for="film in listaFilm" :key="`${film.id}`">
  <li>{{film.title}}</li>
  <li>{{film.original_title}}</li>
  <li>{{film.vote_average}}</li>
</ul>
</div> -->
  </div>
</div>
</template>

<script>
import CardComp from '@/components/CardComp';


export default {
  name:'MainComp',
  components:{
    CardComp
  },
  props:{
    listaFilm:Array,
    titleCards:String
  }

}
</script>


<style langh="scss" scoped>
.container{
  background-color: #434343;
  min-height: 100%;
}
.card-wrapper{
  display: flex;
  flex-wrap: wrap;
  text-align: center;
}
</style>