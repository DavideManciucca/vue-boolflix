<template>
  <div class="container-cards">
    
    
      <!-- <img class="copertina"  :src="`https://image.tmdb.org/t/p/w200${cardData.poster_path}`" alt="">
    
    
    
      <h1>{{cardData.title || cardData.name}}</h1>
      <p>{{cardData.original_title || cardData.original_name}}</p>
      <img class="img_png" v-if="flags.includes(cardData.original_language)" :src="require(`../assets/img/${cardData.original_language}.png`)" alt="">
      <p v-else>Lingua Originale:{{cardData.original_language}}</p>
      <p>{{cardData.vote_average}}</p> -->


    <!--  prova -->


    <div class="flip-card">
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <img v-if="cardData.poster_path != null" class="copertina" :src="`https://image.tmdb.org/t/p/w200${cardData.poster_path}`">
      <img class="copertina" v-else src="https://upload.wikimedia.org/wikipedia/commons/9/95/No_immagine_disponibile.svg" alt="">
    </div>
    <div class="flip-card-back">
      <h1 class="title">{{cardData.title || cardData.name}}</h1>
      <p>{{cardData.original_title || cardData.original_name}}</p>
      <img class="img_png" v-if="flags.includes(cardData.original_language)" :src="require(`../assets/img/${cardData.original_language}.png`)" alt="">
      <p v-else>Lingua Originale:{{cardData.original_language}}</p>
      <p>{{cardData.vote_average}}</p>
      
      <div class="description">{{cardData.overview}}</div>
      
    </div>
  </div>
</div>




     </div>
 
</template>

<script>
// import LangFlag from 'vue-lang-code-flags';

export default {
  name:'CardComp',
  data(){
    return{
      flags:['it', 'en']
    }
  },
  
  
  components:{
// LangFlag
  },
  props:{
    cardData:Object
  }
}
</script>

<style langh="scss" scoped>

.container-cards{
  width: calc(100% / 5);
}.copertina{
  /* height: 400px; */
  height: 300px;
  width: 200px;
  }
.img_png{
  height: 10px;
  width: 20px;
}.description{
  overflow-y: scroll;
  height: 150px;
  
}.title{
  font-size: 15px;
}

.flip-card {
  background-color: transparent;
  width: 200px;
  height: 300px;
  perspective: 1000px;
  margin: 1rem;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;

}

.flip-card-back {
  /* background-color: #2980b9; */
  background-color: black;
  color: white;
  text-align: initial;
 font-size: 12px;
  transform: rotateY(180deg);
}



</style>