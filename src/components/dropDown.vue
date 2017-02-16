<template>
  <div class="dropDown">
    <!-- Dropdown menu to set company -->
    <p id="drop-down-menu">Company:
    <select v-model="currentCompany" class="company">
      <option value="Select a company to see tweets and stock data">Select a Company</option>
      <option value="Boeing">Boeing</option>
      <option value="Fiat-Chrysler">Fiat-Chrysler</option>
      <option value="Ford">Ford</option>
      <option value="Toyota">Toyota</option>
      <option value="Nordstrom">Nordstrom</option>
      <option value="Rexnord">Rexnord</option>
      <option value="United Technologies">United Technologies</option>
      <option value="General Motors">General Motors</option>
    </select>
  </br>
    <div class="container" id="company-container">
      <div class="row">
      <div class="col-6" id="company-name">{{ currentCompany }}</div>
    </div>
  </div>
  <about :currentCompany="currentCompany" :tweets="tweets"></about>
</div>

</template>

<script>
import about from '../components/about'
export default {
  props: [
    'tweets'
  ],
  data () {
    return {
      currentCompany: ''
    }
  },
  methods: {
  },
  components: {
    about
  }
}
</script>
<style>
#app {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 18px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 20px;
  padding:20px;
  background-color: #F5F8FA;
  /* border: thin grey solid; */
}
#drop-down-menu {
  margin-top: 2em;
  margin-left: 3.5em;
  margin-bottom: 2em;
  text-align: center;
  font-size: 25px;
}
#company-name {
  font-family: 'Mukta Vaani', sans-serif;
  font-weight: bold;
  font-size: 50px;
  float: left;
  margin-left: 2em;
  margin-top: 2em;
}
</style>
