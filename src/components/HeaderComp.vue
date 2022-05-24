<template>
  <div class="container-header"> 
    <div class="logo"><img src="../assets/img/netflix.png" alt=""></div>
    <input
  v-model.trim="text" @keyup.enter="$emit('search', text)"
   type="text" placeholder="Cerca ciò che desideri">

    <!-- <SelectComp /> -->

   <!-- <a  href="#">Film</a>
   <a  href="#">Serie Tv</a> -->

    <!-- <SelectComp @changedGenere="cambiaGenere"
    /> -->
 </div>
</template>

<script>
// import SelectComp from '@/components/SelectComp';
export default {
  name:'HeaderComp',
  components:{
  },
  data(){
    return{
      text:'',
      flagSerieTv:false,
      flagFilm:false
    }
  },
  methods:{
    
  },
    

}
</script>

<style langh="scss" scoped>
.container-header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
  background-color: black;
  padding: 5px;
}.logo{
  width: 30px;
  height: 40px;
}.logo img{
  height: 100%;
}

</style>