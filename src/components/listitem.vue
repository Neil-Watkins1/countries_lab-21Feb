<template lang="html">
  <option :value="country">{{country.name}}</option>
</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: 'list-item',
  props: ['country'],
  methods: {
    handleClick(){
      eventBus.$emit('picked-country', this.country);
    }
  }

}
</script>

<style lang="css" scoped>
</style>
