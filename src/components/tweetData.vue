<template>
  <div id="app">
    <div class="tweetData">
    <p><img src="static/dt.jpg" style="float:left; width:50px; height:50px; border:1px solid white; border-radius:5px; margin:1px 10px 3px 0px;">
      <span style="color:#1DA1F2; padding-left:10px;">@realDonaldTrump:</span> {{ currentTweettext }} </p>
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
  border: 1px solid grey;
  border-radius:5px;
  padding: 4px;
  background-color: lightblue;
  margin: 15px;
  color: black;
}

</style>
