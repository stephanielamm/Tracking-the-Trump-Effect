<template>
  <div class="container box">
  <div class="row about">
  <div class="col col-lg-12">
  <p>{{ currentAbout }}</p>
</div>
</div>

<div class="row">
  <div class="col-lg-5">
    <tweetData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </tweetData>
  </div>
<div class="col-lg-5 chart">
    <stockData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </stockData>
</div>
</div>

<div class="row analysis">
  <div class="col col-lg-12">
    <analysis :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
    </analysis>
  </div>
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
  padding: 1em 3em 3em 3em;
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
</style>
