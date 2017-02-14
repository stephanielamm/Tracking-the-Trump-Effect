<template>
  <div id="app">
  {{ message }}
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
  font-size: 30px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: orange;
  margin-top: 60px;
  padding:40px;
  border: thin grey solid;
}
</style>
