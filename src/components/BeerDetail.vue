<template lang="html">
<div>
<img :src="selectedBeer.image_url" height="120" width="60"alt="beer-piccs">
<p>NAME: {{selectedBeer.name}}</p>
<p>TAGLINE: {{selectedBeer.tagline}}</p>
<p>ALCHOOL % : {{selectedBeer.abv}}</p>
<p>ingredients:</p>
<p>Malts:</p>
<ul>
  <li v-for="(malt, index) in showMalts" :key="index">{{malt}}</li>
</ul>
<p>Hops:</p>
<ul>
  <li v-for="(hops, index) in showHops" :key="index">{{hops}}</li>
</ul>
<p>Yeast: {{selectedBeer.ingredients.yeast}}</p>

</div>
</template>

<script>
export default {
  name: 'BeerDetail',
  props: ['selectedBeer'],
  computed: {
    showMalts: function(){
      return this.selectedBeer.ingredients.malt.map((malt) => malt.name)
    },
    showHops: function () {
    return this.selectedBeer.ingredients.hops.map((hoop) => hoop.name)

    }
  }
}
</script>

<style lang="css" scoped>

</style>
