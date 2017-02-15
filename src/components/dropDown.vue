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
</style>
