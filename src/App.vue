<template>
  <div id="app">
      <Intro></Intro>
      <dropDown :tweets="tweets"></dropDown>
      </div>
</div>
</template>

<script>
import axios from 'axios'
import Intro from './components/Intro'
import dropDown from './components/dropDown'

export default {
  name: 'app',
  components: {
    Intro,
    dropDown
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
  color: #696969;
}

</style>
