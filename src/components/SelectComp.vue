<template>
  <div><form>
      <select v-model="genere" @change="$emit('changedGenre', genere)" name="" id="">
        <option value="Film">Film</option>
        <option value="Serie Tv">Serie Tv</option>
        
      </select>
      </form></div>
</template>

<script>
export default {
  name:"SelectComp",
 data(){
   return{
     genere:'Film'
   }
 },
  
}
</script>

<style lang="scss" scoped>

</style>