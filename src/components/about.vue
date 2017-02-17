<template>
  <div class="container box">
  <div class="row about">
  <div class="col col-lg-12">
  <p>{{ currentAbout }}</p>
</div>
</div>

<div class="row">
  <div class="col-5">
    <tweetData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </tweetData>
  </div>
<div class="col-5 chart">
    <stockData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </stockData>
</div>
</div>
</br>
<div class="row analysis">
  <div class="col-12">
    <analysis :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </analysis>
  </div>
</div>
<div class="row footer">
<div class="col-12">Stock data from Yahoo Finance. Tweets from @realDonaldTrump. Company information from Wikipedia.</div>
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
      currentCompanyData () {
        return this.tweets[this.currentCompany]
      },
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
.box {
  background-color: #F5F8FA;
  width: 85%;
  height: auto;
  margin-bottom: 75px;
  padding: 1em 3em 0.2em 3em;
}
.about {
  font-size: 25px;
}
.chart {
  float: right;
}
.analysis {
  font-size: 25px;
}
.footer {
  width: 100%;
  font-size: 12px;
  color: grey;
  text-align: left;
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
