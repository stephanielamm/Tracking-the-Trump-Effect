<template>
  <div id="app">
    <!-- Twitter Box will only show if a company is selected -->
    <div v-show="currentCompany !== ''" class="container tweetData">
    <p><img src="static/dt.jpg" style="float:left; width:55px; height:55px; border:1px solid white; border-radius:5px; margin:3px 8px 8px 0px;">
      <span style="font-weight:bold; margin-bottom:0px; font-size:22px;">Donald J. Trump</span>
    </br>
      <span style="color:#1DA1F2; margin-top:0px; font-size:15px;" >@realDonaldTrump</span>
    </br></br>
      <span style="font-size: 22px; line-height: 0.8;">{{ currentTweettext }}</span> </br>
      <span style="font-size:12; color:#696969;">{{ currentTweettime }} - {{ currentTweetdate }}</span>
    </p>
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
    },
    currentTweetdate () {
      if (this.currentCompanyData) return this.currentCompanyData.date
    },
    currentTweettime () {
      if (this.currentCompanyData) return this.currentCompanyData.time
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
  float: left;
}
</style>
