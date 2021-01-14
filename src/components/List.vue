<template lang="html">
 <ul>
     <li v-for="item in items" :value="item">{{ item }}<li/>
<ul/>
  
</template>

<script>
export default {
    props: ['item'],
    methods: {
    // handleClick(){
        
    // }
    }
         
     
 }

</script>

<style>

</style>