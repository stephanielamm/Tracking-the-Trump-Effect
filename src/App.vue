<template>
  <div id="app">
     {{ message }} 
    <tweetData :tweetData="tweets">
    </tweetData>
  </div>
</template>

<script>
import axios from 'axios'
import tweetData from './components/tweetData.vue'

export default {
  name: 'app',
  components: {
    tweetData
  },
  data () {
    return {
      message: 'test message',
      tweets: []
    }
  },
  mounted () {
    axios.get('/static/twitter-data.json')
    .then((response) => {
      // console.log(response.data)
      this.tweets = response.data
    })
  }
}
</script>

<style>
#app {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 30px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: orange;
  margin-top: 60px;
  padding:40px;
  /* border: thin grey solid; */
}
</style>
