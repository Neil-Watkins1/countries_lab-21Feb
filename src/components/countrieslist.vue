<template lang="html">
<div>
  <select v-model="selectedCountry" v-on:change="handleSelect">
    <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
  </select>
</div>

</template>

<script>
import listItem from './listitem.vue';
import {eventBus} from '../main.js'

export default {
  data(){
    return{
      selectedCountry: null
    }
  },
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": listItem
  },
  methods: {
    handleSelect(){
      eventBus.$emit('picked-country', this.selectedCountry)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
