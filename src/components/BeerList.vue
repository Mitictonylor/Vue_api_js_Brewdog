<template lang="html">
<div >
  <ul>
<list-beer v-for="(beer,index) in beers" :key="index" :beer="beer"></list-beer>
  </ul>
</div>
</template>

<script>
import BeerItem from './BeerItem.vue'
export default {
  name: "beer-list",
  props:['beers'],
  components:{
    "list-beer": BeerItem
  }

}
</script>

<style lang="css" scoped>
</style>
