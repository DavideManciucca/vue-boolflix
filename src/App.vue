<template>
  <div >
    <HeaderComp 
    @search="userSearch"
    />

    <MainComp 
    :listaFilm="listaFilm"
    :listaSerieTv="listaSerieTv"
    />

  </div>
</template>

<script>
import HeaderComp from '@/components/HeaderComp';
import MainComp from '@/components/MainComp';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      apiUrl:'https://api.themoviedb.org/3/search/movie',
      myApiParams:{
        api_key:'71a30d6971b91b949b6f3933c61ff2ad',
        language:'it-IT',
        query:'harry potter'
        // original_title:'',
        // vote_average:'',
        // poster_path:'',
      },
      // listaFilm:[],
      listaSerieTv:[],
      listaFilm:[],


    }
  },
  mounted(){
    // this.callApi();
  },
  methods:{
    callApi(){
      axios.get(this.apiUrl,{
        params: this.myApiParams
      })
      .then(r=>{
        console.log(r.data.results);
        // this.listaFilm.push(r.data.results)
        this.listaFilm = r.data.results
        console.log('TEST XXXXXXXXX',this.listaFilm)
      })
      .catch(e=>{
        console.log(e);
      })
    },
    userSearch(strUser){
      this.myApiParams.query = strUser
      console.log('test',strUser);
      this.callApi();
    }
  }
}
</script>

<style lang="scss">

</style>
