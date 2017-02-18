<template>
  <div class="container box">
  <div class="row about">
  <div class="col col-lg-12">
  <p>{{ currentAbout }}</p>
</div>
</div>
<div class="row">
  <div class="col-8">
    <!-- Tweet Component -->
    <tweetData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </tweetData>
  </div>
<div class="col-3 analysis">
  <!-- Analysis Component -->
  <analysis :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
  </analysis>
</div>
</div>
</br>
<div class="row">
  <div class="col-12 chart">
    <!-- Stocks Component -->
    <stockData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </stockData>
  </div>
</div>
<div class="row footer">
  <!-- Credit for information used. See README for details. -->
<div class="col-12">Stock charts from Yahoo Finance. Tweets from @realDonaldTrump. Company information from Wikipedia with Analysis from Quartz.</div>

</div>
</div>

</template>
  <script>
  import tweetData from '../components/tweetData'
  import analysis from '../components/analysis'
  import stockData from '../components/stockData'
  export default {
    props: [
      'tweets',
      'currentCompany'
    ],
    data () {
      return {
      }
    },
    computed: {
      // Creates a variable that contains the values of the company slected from the drop down menu
      currentCompanyData () {
        return this.tweets[this.currentCompany]
      },
    // Creates a variable that grabs the about value from the company selected from the drop down menu
      currentAbout () {
        if (this.currentCompanyData) return this.currentCompanyData.about
      }
    },
    components: {
      tweetData,
      analysis,
      stockData
    },
    methods: {
    }
  }
</script>
<style>
/* Content Box Styling */
.box {
  background-color: #F5F8FA;
  width: 85%;
  height: auto;
  margin-bottom: 75px;
  padding: 1em 3em 0.2em 3em;
}
/* About Company Font Styling */
.about {
  font-size: 25px;
}
/* Analysis Styling */
.analysis {
  font-size: 25px;
  float: right;
  font-style: italic;
}
/* Credits Styling */
.footer {
  width: 100%;
  font-size: 15px;
  color: #696969;
  float:right;
}
/* For Desktop: */
.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}

    /* For Mobile */
@media only screen and (max-width: 1275px) {
    [class*="col-"] {
        width: 100%;
    }
    .footer {
      font-size: 9px;
    }
}
</style>
