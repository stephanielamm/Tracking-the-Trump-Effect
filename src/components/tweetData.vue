<template>
  <div id="app">
<!-- {{ message }} -->
  </div>
</template>

<script>
export default {
  name: 'app',
  props: [
    'tweetData'
  ],
  data () {
    return {
      message: 'tweetData message test'
    }
  },
  mounted () {
    console.log(this.tweets)
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
}#company-logo {
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
#explanatory-text {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
}
</style>
