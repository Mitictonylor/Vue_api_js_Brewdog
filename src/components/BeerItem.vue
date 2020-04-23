<template lang="html">
<div>
  <li v-on:click="handleClickOnName">{{beer.name}}</li>
  <button v-on:click="handleClickOnButton"type="button" name="Add to Favs">Add to Favs</button>
</div>
</template>

<script>
import {eventBus} from'../main.js'
export default {
  name: "beer-item",
  props:["beer"],
  methods:{
    handleClickOnName: function(){
          eventBus.$emit('selected-beer', this.beer )
    },
    handleClickOnButton: function(){
          eventBus.$emit('add-to-favs', this.beer)
    }

  }
}
</script>

<style lang="css" scoped>
</style>
