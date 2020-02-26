<template>
  <div id="app">
    <h1>Countries List</h1>
     <div class="flex-container">
       <countries-list :countries='countries'></countries-list>
       <country-detail :country='selectedCountry'></country-detail>
     </div>

  </div>

</template>


<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import {eventBus} from './main.js'

export default {
  name: 'app',
   data(){
     return{
       countries: [],
       selectedCountry: null
     }
   },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(data => this.countries = data)

    eventBus.$on('country-selected', (country) =>{
      this.selectedCountry = country;
    })
  },

  components: {
   "countries-list": CountriesList,
   "country-detail": CountryDetail

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.flex-container {
  justify-content: space-between;
  display: inline-flex;
}

ul {
  list-style: none;
}

h1 {
  color: #dda0dd;
  border-style: dotted;
  border-color: #dda0dd;
  background-color: rgba(0,0,0,.03);
  text-align: center;
}
</style>
