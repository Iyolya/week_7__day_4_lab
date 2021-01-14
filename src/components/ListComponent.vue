<template lang="html">
    <div>
        <li v-on:click="handleListClick">{{ beerObject.name }}</li>
        <button v-bind:class="isFavourite ? hidden : visible"  v-on:click="handleFavouriteClick">Favourite</button>
    </div>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    props: ['beerObject'],
    methods: {
    handleListClick(){
        eventBus.$emit('beer-selected', this.beerObject)
        },

    handleFavouriteClick(){
        eventBus.$emit('favourite-selected', this.beerObject)
        }
    }
 }

</script>

<style lang="css">
.hidden {
    display: none;
}
</style>
