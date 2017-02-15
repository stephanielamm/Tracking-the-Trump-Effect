<template>
  <div id="app">
    <!-- Dropdown menu to set company -->
    <p>Company:
    <select v-model="company" class="company">
      <option value="">Select a Company</option>
      <option value="Boeing">Boeing</option>
      <option value="Fiat-Chrysler">Fiat-Chrysler</option>
      <option value="Ford">Ford</option>
      <option value="Toyota">Toyota</option>
      <option value="Nordstrom">Nordstrom</option>
      <option value="Rexnord">Rexnord</option>
      <option value="United Technologies">United Technologies</option>
      <option value="General Motors">General Motors</option>
    </select>
       <span>{{ company }}</span>
      </p>
  <!--  <tweetData :tweetData="tweets">
  </tweetData> -->
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
      tweets: [],
      company: ''
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
  font-size: 25px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 20px;
  padding:20px;
  /* border: thin grey solid; */
}
</style>
