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
    console.log(this.tweets)
  }
}
</script>

<style>

</style>
