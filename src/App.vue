<template>
  <div id="app">
      <Intro></Intro>
      <dropDown :tweets="tweets"></dropDown>
      <footerBar></footerBar>
  </div>
</template>

<script>
import axios from 'axios'
import Intro from './components/Intro'
import dropDown from './components/dropDown'
import tweetData from './components/tweetData'
// import stockData from './components/stockData'
// import analysis from './components/analysis'
import footerBar from './components/footerBar'

export default {
  name: 'app',
  components: {
    Intro,
    dropDown,
    tweetData,
    footerBar
  },

  data () {
    return {
      tweets: []
    }
  },
  mounted () {
    axios.get('/static/twitter-data.json')
    .then((response) => {
      this.tweets = response.data
    })
  },
  methods: {
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
