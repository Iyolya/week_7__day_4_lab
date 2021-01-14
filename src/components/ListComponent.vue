<template lang="html">
     <li v-on:click="handleListClick">{{ beerObject.name }}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    props: ['beerObject'],
    methods: {
    handleListClick(){
        eventBus.$emit('beer-selected', this.beerObject)
        },

    // handleFavouriteClick(){
    //     eventBus.$emit('favourite-selected', this.beer)
    // }
    }
 }

</script>

<style></style>

</style>