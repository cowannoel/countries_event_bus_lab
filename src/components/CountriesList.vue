<template lang="html">
    <ul class="country-list-flex">
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul>
</template>

<script>

import ListItem from './ListItem.vue';


export default {
  name: "countries-list",
  props: ['countries'],
  components: {
    'list-item': ListItem
  }
}
</script>

<style lang="css" scoped>
  .country-list-flex {
    flex: 1;
    padding-left: 0px;
  }
</style>
