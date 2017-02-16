<template>
  <div id="app">
    <div class="row">
    <div class="col-6" id="tweet-box">
    {{ tweettext }}
      </div>
  </div>
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
      tweets: [],
      tweettext: 'A tweet from @realDonaldTrump mentioning that company will appear here.'
    }
  },
  mounted () {
    console.log(this.tweets)
  }
}
</script>

<style>
#tweet-box {
  float: left;
  margin-left: 3.5em;
  margin-top: 2em;
  margin-bottom: 2em;
}

</style>
