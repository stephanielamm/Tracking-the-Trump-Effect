<template>
  <div id="app">
    <div class="container tweetData">
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

}
.tweetData {
  font-family: 'Mukta Vaani', sans-serif;
  height: 230px;
  width: 500px;
  float: left;
  border: 4px solid #DCF5FF;
  border-radius:5px;
  padding: 8px;
  background-color: white;
  margin: 25px 0px;
  color: black;
  font-size: 25px;
}
@media only screen and (max-width: 1275px) {
    /* For mobile phones: */
    .tweetData {
      width: 100%;

    }
}

</style>
