<template lang="html">
     <li v-on:click="handleListClick">{{ beer.name }}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    props: ['beersData'],
    methods: {
    handleListClick(){
        eventBus.$emit('beer-selected', this.beer)
        },

    // handleFavouriteClick(){
    //     eventBus.$emit('favourite-selected', this.beer)
    // }
    }
 }

</script>

<style></style>

</style>