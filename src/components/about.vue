<template>
  <div class="about">
  <div class="container">
  <div class="row" id="company-about">
  <p>About the company: {{ currentAbout }}</p>
</div>
</div>
<tweetData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">

</tweetData>
<analysis :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
</analysis>
<stockData :currentCompany="currentCompany" :tweets="tweets" :currentCompanyData="currentCompanyData">
</stockData>
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
/* About company styling */
#company-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
  margin-top: 0.1em;
}
</style>
