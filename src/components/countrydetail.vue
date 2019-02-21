<template lang="html">
<div v-if="country">
<h1>{{country.name}}</h1>
<h2>{{country.region}}</h2>
<h3>{{country.capital}}</h3>
<p>{{country.population}}</p>

</div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']

}
</script>

<style lang="css" scoped>
</style>
