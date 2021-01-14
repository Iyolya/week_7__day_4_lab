<template lang="html">
  <div>
    <h1>Brew Dog</h1>
    <div class="components">
      <all-beers/> 
      <beers-detail/>
      <favourites/>
    </div>
  </div>
</template>

<script>
import AllBeers from './components/AllBeers.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
    data(){
        return {
            beersData: []
        }
    },
    components: {
        "favourites": Favourites,
        "beers-detail": BeersDetail,
        "all-beers": AllBeers
    },
    mounted(){
      fetch('https://api.punkapi.com/v2/beers')
      .then(res => res.json())
      .then(importedFromAPI => this.beersData = importedFromAPI)
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
