<template>
  <div v-if="selectedBeer"> <!-- if false don't render, shoes away the null rendering error on page load -->
      <h2>Detail</h2>
      {{ selectedBeer.name }}
      {{ selectedBeer.abv }}
      {{ selectedBeer.attenuation_level }}
      {{ selectedBeer.attenuation_breswers_tips }}
      {{ selectedBeer.description }}
      {{ selectedBeer.ingredients }}
  </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['selectedBeer']
}
</script>

<style>

</style>