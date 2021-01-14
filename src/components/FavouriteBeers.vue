<template lang="html">
    <div>
        <h2>Favourite beers</h2>
        <ul>
            <list-component v-for="(beer, index) in favouriteBeers" :beerObject="beer" :key="index"></list-component>
        </ul>
    </div>
</template>

<script>
import ListComponent from './ListComponent.vue'
export default {
    name: "favourite-beers",
    props: ['favouriteBeers'],
    components: {
        "list-component": ListComponent
    }
}
</script>

<style>

</style>