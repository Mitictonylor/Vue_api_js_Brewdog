<template lang="html">
<div >
<ul>
  <li v-for="(beer,index) in favBeers" :key="index">{{beer.name}}<button v-on:click="RemoveFromFavs(index)"type="button" name="Remove from favs">Remove from favs</button></li>

</ul>
</div>
</template>

<script>
export default {
  name:"FavBeer",
  props: ['favBeers'],
  methods:{
    RemoveFromFavs: function(index){
      this.favBeers.splice(index,1)

  }
}
}
</script>

<style lang="css" scoped>
</style>
