<template>
  <div class="app" >
    <HeaderComp 
    @search="userSearch" 
    />


    <MainComp v-if="listaFilm.length > 0" titleCards="Film" :listaFilm="listaFilm"/>
    <MainComp v-if="listaSerieTv.length >0" titleCards="Serie Tv" :listaFilm="listaSerieTv" />
    <!-- <MainComp   titleCards="Film Popolari"   :popFIlm="popularFilms" /> -->

      <h1 v-if="listaFilm.length===0 && listaSerieTv.length===0">Fai la tua ricerca o riprova a digitare correttamente </h1>
    <!-- <MainComp 
    :listaFilm="listaFilm"
    :listaSerieTv="listaSerieTv"
    /> -->

  </div>
</template>

<script>

import HeaderComp from '@/components/HeaderComp';
import MainComp from '@/components/MainComp';
import axios from 'axios';
// import LangFlag from 'vue-lang-code-flags';


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    // LangFlag
  },
  data(){
    return{
      popularMoviesUrl:'https://api.themoviedb.org/3/trending/movie/week?api_key=83c397b63c322fd6a37d6c5ec3d5f6de',
      apiUrl:'https://api.themoviedb.org/3/search/movie',
      apiTVUrl:'https://api.themoviedb.org/3/search/tv',
      myApiParams:{
        api_key:'71a30d6971b91b949b6f3933c61ff2ad',
        // language:'<lang-flag iso="it"/>',
        language:'it-IT',
        query:''
        // original_title:'',
        // vote_average:'',
        // poster_path:'',
      },
      // listaFilm:[],
      listaSerieTv:[],
      listaFilm:[],
      popularFilms:[]


    }
  },
  mounted(){
    // this.callApi();
    this.popularMovies()
  },
  methods:{
    callApi(){
      axios.get(this.apiUrl,{
        params: this.myApiParams
      })
      .then(r=>{
        console.log(r.data.results);
    
        this.listaFilm = r.data.results
        console.log('TEST XXXXXXXXX',this.listaFilm)
      })
      .catch(e=>{
        console.log(e);
      })
    },
    callTvApi(){
      axios.get(this.apiTVUrl,{
        params : this.myApiParams
      })
      .then(r=>{
        console.log(r.data.results);
        this.listaSerieTv = r.data.results
        console.log('test array serie tv')
      })
      .catch(e=>{
        console.log(e);
      })
    },
    userSearch(strUser){
      this.myApiParams.query = strUser
      console.log('test',strUser);
      if(strUser.length > 0){
      this.callApi();
      this.callTvApi();

      }
    },
     popularMovies(){
      axios.get(this.popularMoviesUrl)
      .then(r =>{
        this.popularFilms = r.data.results;
        console.log(this.popularFilms)
      })
    },
   
  }
}
</script>

<style lang="scss" >
.app{
  background-color: #434343;
  min-height: 100vh;
}


</style>
