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
#company-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
  margin-top: 0.1em;
}
/* Twitter Styling */
#tweet-box {
  float: left;
  margin-left: 3.5em;
  margin-top: 2em;
  margin-bottom: 2em;
}
/* Stock Chart Styling */
#stock-chart {
  float: right;
  margin-right: 2em;
  margin-top: 2em;
  margin-bottom: 2em;
}
/* Explanatory Text Box Styling */
#analysis {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
}
</style>
