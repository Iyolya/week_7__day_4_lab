<template lang="html">
<div>
<h2>List of beers</h2>
<ul>
    <list-component v-for="(beer, index) in beersData" :beerObject="beer" :key="index"></list-component>
</ul>
</div>
  
</template>

<script>
import ListComponent from './ListComponent.vue'
export default {
    name: 'all-beers',
    props: ['beersData'],
    components: {
        "list-component": ListComponent
    }
}
</script>

<style lang="css" scoped>

</style>