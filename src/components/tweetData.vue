<template>
  <div id="app">
    <div class="tweetData">
    <div class="row">
    <div class="col">
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
#app {
  background-color: #F5F8FA;
}
.tweetData {
  float: left;
  color: #1DA1F2;
}

</style>
