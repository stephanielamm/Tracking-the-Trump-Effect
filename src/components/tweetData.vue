<template>
  <div id="app">
    <div class="tweetData">
    <div class="row">
    <div class="col-6" id="tweet-box">
    <p>@realDonaldTrump: {{ currentTweettext }} </p>
      </div>
  </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'tweetData',
  props: [
    'tweets',
    'currentCompany',
    'currentCompanyData'
  ],
  data () {
    return {
    }
  },
  computed: {
    currentTweettext () {
      if (this.currentCompanyData) return this.currentCompanyData.tweettext
    }
  },
  mounted () {
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
