<template>
  <div id="app">
      <Intro></Intro>
      <dropDown :tweets="tweets"></dropDown>
      <!--   <tweetData></tweetData>
      <stockData></stockData>
      <analysis></analysis> -->
      <footerBar></footerBar>
  <!-- <tweetData
  :about="about"
  :tweettext="tweettext"
  :analysis="analysis"
  :logo="logo"
  >
  </tweetData> -->
  </div>
</template>

<script>
import axios from 'axios'
import Intro from './components/Intro'
import dropDown from './components/dropDown'
// import logo from './components/logo'
import tweetData from './components/tweetData'
// import stockData from './components/stockData'
// import analysis from './components/analysis'
import footerBar from './components/footerBar'

export default {
  name: 'app',
  components: {
    Intro,
    dropDown,
  //  about,
  //  logo,
    tweetData,
  //  stockData,
  //  analysis,
    footerBar
  },

  data () {
    return {
      tweets: []
    //  logo: '',
    //  analysis: 'Text analyzing the stock price will appear here',
    //  tweettext: 'A tweet from @realDonaldTrump mentioning that company will appear here.'
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
