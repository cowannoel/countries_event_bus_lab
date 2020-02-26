<template lang="html">
  <li v-on:click="handleClick">{{country.name}}</li>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'list-item',
  props: ['country'],
  methods: {
    handleClick(){
      console.log('country', this.country)
    eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
