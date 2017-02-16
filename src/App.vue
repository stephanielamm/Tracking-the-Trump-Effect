<template>
  <div id="app">

      <Intro></Intro>
      <dropDown></dropDown>

    <!-- Dropdown menu to set company -->

  <tweetData
  :company="company"
  :about="about"
  :tweettext="tweettext"
  :analysis="analysis"
  :logo="logo"
  >
  </tweetData>
  </div>
</template>

<script>
import axios from 'axios'
import Intro from './components/Intro'
import dropDown from './components/dropDown'
// import about from './components/about'
// import logo from './components/logo'
import tweetData from './components/tweetData'
// import stockData from './components/stockData'
// import analysis from './components/analysis'

export default {
  name: 'app',
  components: {
    Intro,
    dropDown,
  //  about,
  //  logo,
    tweetData // ,
  //  stockData,
  //  analysis
  },

  data () {
    return {
      message: 'test message',
      tweets: [],
      company: 'Select a company to see tweets and stock data',
      logo: '',
      about: 'Text about the company will appear here.',
      analysis: 'Text analyzing the stock price will appear here',
      tweettext: 'A tweet from @realDonaldTrump mentioning that company will appear here.'
    }
  },
  mounted () {
    axios.get('/static/twitter-data.json')
    .then((response) => {
      this.tweets = response.data
    })
  },
  methods: {
  //  show: function (x) {
  //    this.currentX = x
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
[v-cloak] {
  display: none;
}

</style>
