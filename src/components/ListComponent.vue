<template lang="html">
    <div>
        <li v-on:click="handleListClick">{{ beerObject.name }}</li>
        <button v-on:click="handleFavouriteClick">Favourite</button>
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

<style></style>
