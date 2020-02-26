<template lang="html">
  <div v-if="country" class="country-detail-flex">
    <h3>{{country.name}}</h3>
    <p>Capital: {{country.capital}} </p>
    <p>Population: {{country.population}} </p>
    <p>Flag: {{country.flag}}</p>

  </div>
</template>

<script>
export default {
  name: 'country-selected',
  props: ['country']
}
</script>

<style lang="css" scoped>
.country-detail-flex {
  flex: 1;
  border-color: black;
}
</style>
