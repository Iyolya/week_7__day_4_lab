<template lang="html">
<ul>
    <list-component v-for="(beerObject, index) in beersData" :beerObject="beer" :key="index"></list-component>
</ul>
  
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