<template>
  <div> <input
  v-model.trim="text" @keyup.enter="$emit('search', text)"
   type="text" placeholder="Cerca ciò che desideri"></div>
</template>

<script>
export default {
  name:'HeaderComp',
  data(){
    return{
      text:''
    }
  }

}
</script>

<style langh="scss" scoped>

</style>