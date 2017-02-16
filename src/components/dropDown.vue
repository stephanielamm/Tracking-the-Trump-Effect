<template>
  <div id="app">
    <!-- Dropdown menu to set company -->
    <p id="drop-down-menu">Company:
    <select v-model="company" class="company">
      <option value="Select a company to see tweets and stock data">Select a Company</option>
      <option value="Boeing (BA)">Boeing</option>
      <option value="Fiat-Chrysler (FCAU)">Fiat-Chrysler</option>
      <option value="Ford (F)">Ford</option>
      <option value="Toyota (TM)">Toyota</option>
      <option value="Nordstrom (JWN)">Nordstrom</option>
      <option value="Rexnord (RXN)">Rexnord</option>
      <option value="United Technologies (UTX)">United Technologies</option>
      <option value="General Motors (GM)">General Motors</option>
    </select>
  </br>
    <div class="container" id="company-container">
      <div class="row">
      <div class="col-6" id="company-name">{{ company }}</div>
      <div class="col-6" id="company-logo">
        <img src="static/boeing-logo.png" alt="Company Logo" style="width:300px;height:100px;">
        </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'app',
  props: {
    'company'
  },

  data () {
    return {
      company: 'Select a company to see tweets and stock data',
      logo: '',
      about: 'Text about the company will appear here.',
      analysis: 'Text analyzing the stock price will appear here',
      tweettext: 'A tweet from @realDonaldTrump mentioning that company will appear here.'
    }
  },
  methods: {

  },
  mounted () {
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
#company-logo {
  float: right;
  margin-top: 1em;
  margin-right: 1em;
}
</style>
