<template lang="html">
  <div>
    <h1>Countries</h1>
    <div class="main-container">
<countries-list :countries='countries'></countries-list>
<country-detail :country="selectedCountry"></country-detail>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/countrieslist.vue';
import CountryDetail from './components/countrydetail.vue';
import {eventBus} from './main.js';

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  components: {
"countries-list": CountriesList,
"country-detail": CountryDetail
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('picked-country', (country) => {
      this.selectedCountry = country;
    }),
    eventBus.$on('picked-country', (country) => {
      this.selectedCountry = country;
    })
  }
}
</script>

<style lang="css" scoped>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
