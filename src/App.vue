<template lang="html">
  <div>
    <h1>Brew Dog</h1>
    <div class="components">
      <all-beers :beersData="beersData" /> 
      <beer-detail :selectedBeer="selectedBeer"  />
      <favourite-beers :favouriteBeers="favouriteBeers"/>
    </div>
  </div>
</template>

<script>
import BeerDetail from './components/BeerDetail.vue'
import FavouriteBeers from './components/FavouriteBeers.vue'
import AllBeers from './components/AllBeers.vue'
import { eventBus } from './main'

export default {
    data(){
        return {
            beersData: [],
            selectedBeer: null,
            favouriteBeers: []
        }
    },
    components: {
        "beer-detail": BeerDetail,
        "all-beers": AllBeers,
        "favourite-beers": FavouriteBeers
    },

    mounted(){
      fetch('https://api.punkapi.com/v2/beers')
      .then(res => res.json())
      .then(importedFromAPI => this.beersData = importedFromAPI)

      eventBus.$on('beer-selected', (beer) => {
        this.selectedBeer = beer
      })
      eventBus.$on('favourite-selected', (beer) => {
        this.favouriteBeers.push(beer) 
      })
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
