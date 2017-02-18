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
  <!-- Credit for Information -->
<div class="col-12">Stock charts from Yahoo Finance. Tweets from @realDonaldTrump. Company information from Wikipedia with Analysis from Quartz.</div>
<!-- Links:
GM Chart: https://finance.yahoo.com/chart/GM#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjNtbyJ9
UTX Chart: https://finance.yahoo.com/chart/UTX#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjNtbyJ9
RXN Chart: https://finance.yahoo.com/chart/RXN#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjFtbyJ9
JWN Chart: https://finance.yahoo.com/chart/JWN#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjNtbyJ9
F Chart: https://finance.yahoo.com/chart/F#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjF5In0%3D
BA Chart: https://finance.yahoo.com/chart/BA#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjJ5In0%3D
TM Chart: https://finance.yahoo.com/chart/TM#eyJtdWx0aUNvbG9yTGluZSI6ZmFsc2UsImJvbGxpbmdlclVwcGVyQ29sb3IiOiIjZTIwMDgxIiwiYm9sbGluZ2VyTG93ZXJDb2xvciI6IiM5NTUyZmYiLCJtZmlMaW5lQ29sb3IiOiIjNDVlM2ZmIiwibWFjZERpdmVyZ2VuY2VDb2xvciI6IiNmZjdiMTIiLCJtYWNkTWFjZENvbG9yIjoiIzc4N2Q4MiIsIm1hY2RTaWduYWxDb2xvciI6IiMwMDAwMDAiLCJyc2lMaW5lQ29sb3IiOiIjZmZiNzAwIiwic3RvY2hLTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoRExpbmVDb2xvciI6IiM0NWUzZmYiLCJyYW5nZSI6IjNtbyJ9
FCAU Chart: https://finance.yahoo.com/chart/FCAU#eyJjdXN0b21SYW5nZUVuZCI6MTQ4NTgzODc5OSwiY3VzdG9tUmFuZ2VTdGFydCI6MTQ4MzMzMzIwMCwibXVsdGlDb2xvckxpbmUiOmZhbHNlLCJib2xsaW5nZXJVcHBlckNvbG9yIjoiI2UyMDA4MSIsImJvbGxpbmdlckxvd2VyQ29sb3IiOiIjOTU1MmZmIiwibWZpTGluZUNvbG9yIjoiIzQ1ZTNmZiIsIm1hY2REaXZlcmdlbmNlQ29sb3IiOiIjZmY3YjEyIiwibWFjZE1hY2RDb2xvciI6IiM3ODdkODIiLCJtYWNkU2lnbmFsQ29sb3IiOiIjMDAwMDAwIiwicnNpTGluZUNvbG9yIjoiI2ZmYjcwMCIsInN0b2NoS0xpbmVDb2xvciI6IiNmZmI3MDAiLCJzdG9jaERMaW5lQ29sb3IiOiIjNDVlM2ZmIn0%3D
Analysis insights from:
Quartz Article: https://qz.com/907408/new-analysis-proves-trumps-tweets-attacking-companies-are-mostly-just-distractions/
Bloomberg: https://www.bloomberg.com/gadfly/articles/2017-01-24/trump-s-tweets-don-t-turn-out-to-be-useful-stock-tips
Reuters: http://www.reuters.com/article/us-usa-trump-rexnord-idUSKBN13S0PU
MSN: https://www.msn.com/en-us/money/markets/president-elect-trump-targets-rexnord-with-a-tweet/vp-AAlbuu0
Financial Times: https://ftalphaville.ft.com/2017/01/06/2181929/stop-worrying-about-trumps-tweets/?ftcamp=engage/capi/widget/client/openft/b2b
WSJ: http://blogs.wsj.com/moneybeat/2016/12/05/rexnord-inches-lower-after-trump-tweets/
Investors.com: http://www.investors.com/news/trump-carrier-reach-deal-on-keeping-jobs-at-indiana-plant/
MarketWatch: http://www.marketwatch.com/story/gms-stock-falls-after-trump-tweet-on-mexico-production-2017-01-03
Company Information From:
FCAU: https://en.wikipedia.org/wiki/Fiat_Chrysler_Automobiles
T: https://en.wikipedia.org/wiki/Toyota
JWN: https://en.wikipedia.org/wiki/Nordstrom
Carrier/UTX: https://en.wikipedia.org/wiki/Carrier_Corporation & https://en.wikipedia.org/wiki/United_Technologies
F: https://en.wikipedia.org/wiki/Ford_Motor_Company
RXN: https://en.wikipedia.org/wiki/Rexnord_Corporation
GM: https://en.wikipedia.org/wiki/General_Motors

-->
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
.analysis {
  font-size: 25px;
  float: right;
}
.footer {
  width: 100%;
  font-size: 15px;
  color: #696969;
  float:right;
}
.analysis {
  font-size: 25px;
  float: right;
  font-style: italic;
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
