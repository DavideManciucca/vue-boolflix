<template>
  <div>
    
    <div>
    <h1>{{cardData.title}}</h1>
    <p>{{cardData.original_title}}</p>
    <p>{{cardData.originel_language}}</p>
    <p>{{cardData.vote_average}}</p>
  </div>

  </div>
</template>

<script>
export default {
  name:'CardComp',
  props:{
    cardData:Object
  }
}
</script>

<style langh="scss" scoped>

</style>