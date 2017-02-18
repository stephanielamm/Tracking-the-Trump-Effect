<template>
  <div id="app">
    <!-- Twitter Box will only show if a company is selected -->
    <div v-show="currentCompany !== ''" class="container tweetData">
    <p><img src="static/dt.jpg" style="float:left; width:55px; height:55px; border:1px solid white; border-radius:5px; margin:3px 8px 8px 0px;">
      <span style="font-weight:bold; padding-bottom:0px; font-size:22px;">Donald J. Trump</span>
    </br>
      <span style="color:#1DA1F2; padding-top:0px; font-size:18px;" >@realDonaldTrump</span></br>
      {{ currentTweettext }}</p>
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
    // Will show tweet based on current company only if current company is not null
    currentTweettext () {
      if (this.currentCompanyData) return this.currentCompanyData.tweettext
    }
  },
  methods: {

  },
  mounted () {
  }
}
</script>

<style>
.tweetData {
  font-family: 'Mukta Vaani', sans-serif;
  width: 100%;
  border: 4px solid #DCF5FF;
  border-radius:5px;
  padding: 8px;
  background-color: white;
  margin: 25px 0px;
  color: black;
  font-size: 25px;
  float: left;
}
</style>
