<template lang="html">
<div >
<h1>BREWDOG BEER LIST</h1>
  <beer-list :beers="beers"></beer-list>
  <beer-detail v-if="selectedBeer" :selectedBeer="selectedBeer"></beer-detail>
  <fav-beer v-if="favouriteBeer.length" :favBeers="favouriteBeer"></fav-beer>
</div>
</template>

<script>
import BeerList from './components/BeerList.vue'
import BeerDetail from './components/BeerDetail.vue'
import FavBeer from './components/FavBeer.vue'

import{eventBus} from './main.js'
export default {
  name: "app",
  data(){
    return{
      beers: [],
      selectedBeer: null,
      favouriteBeer: []
  }
},
mounted(){
  fetch("https://api.punkapi.com/v2/beers")
  .then(result => result.json())
  .then(beers => this.beers = beers );

eventBus.$on('selected-beer', (beer) =>{
  this.selectedBeer = beer} );

eventBus.$on('add-to-favs', (beer) =>{
  if (this.favouriteBeer.includes(beer)){
    alert("Beer already in your favourites")
  }else{
  this.favouriteBeer.push(beer)}})
},
components:{
    "beer-list": BeerList,
    'beer-detail': BeerDetail,
    'fav-beer': FavBeer
},
methods:{

},
computed:{

}
  }

</script>

<style lang="css" scoped>

</style>
