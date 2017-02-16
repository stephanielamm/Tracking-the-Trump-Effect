<template>
  <div id="app">

      <Intro></Intro>

    <!-- Dropdown menu to set company -->
    <p id="drop-down-menu">Company:
    <select v-model="company" class="company">
      <option value="Select a company to see tweets and stock data">Select a Company</option>
      <option value="Boeing (BA)">Boeing</option>
      <option value="Fiat-Chrysler (FCAU)">Fiat-Chrysler</option>
      <option value="Ford (F)">Ford</option>
      <option value="Toyota (TM)">Toyota</option>
      <option value="Nordstrom (JWN)">Nordstrom</option>
      <option value="Rexnord (RXN)">Rexnord</option>
      <option value="United Technologies (UTX)">United Technologies</option>
      <option value="General Motors (GM)">General Motors</option>
    </select>
  </br>
    <div class="container" id="company-container">
      <div class="row">
      <div class="col-6" id="company-name">{{ company }}</div>
      <div class="col-6" id="company-logo">
        <img src="static/boeing-logo.png" alt="Company Logo" style="width:300px;height:100px;">
        </div>
    </div>
    <div class="row" id="company-about">
      <p> {{ about }}</p>
      </div>
    <div class="row">
    <div class="col-6" id="tweet-box">
    {{ tweettext }}
      </div>
    <div class="col-6" id="stock-chart">
      This is where the stock chart will go.
    <!--  <div id="container" style="height: 350px; min-width: 510px"></div>
      <script>
      // code from HighStocks; will need to figure out how to get relevant stock data
      $.getJSON('https://www.highcharts.com/samples/data/jsonp.php?filename=aapl-c.json&callback=?', function (data) {
        // Create the chart
      Highcharts.stockChart('container', {
        rangeSelector: {
            selected: 1
        },
        title: {
            text: 'AAPL Stock Price'
        },
        series: [{
            name: 'AAPL',
            data: data,
            tooltip: {
                valueDecimals: 2
            }
        }]
    });
});
</script> -->
      <!-- will have component for stock chart (made with Highstock API) (to right of the page) -->
      </div>
        </div>
      <div class="row" id="analysis">
      <div class="col-12">
      <p>{{ analysis }}</p>
    </div>
  </div>
  </div>
      </p>
  <tweetData
  :company="company"
  :about="about"
  :tweettext="tweettext"
  :analysis="analysis"
  :logo="logo"
  >
  </tweetData>
  </div>
</template>

<script>
import axios from 'axios'
import Intro from './components/Intro'
// import dropDown from './components/dropDown'
// import about from './components/about'
// import logo from './components/logo'
import tweetData from './components/tweetData'
// import stockData from './components/stockData'
// import analysis from './components/analysis'

export default {
  name: 'app',
  components: {
    Intro,
  //  dropDown,
  //  about,
  //  logo,
    tweetData // ,
  //  stockData,
  //  analysis
  },

  data () {
    return {
      message: 'test message',
      tweets: [],
      company: 'Select a company to see tweets and stock data',
      logo: '',
      about: 'Text about the company will appear here.',
      analysis: 'Text analyzing the stock price will appear here',
      tweettext: 'A tweet from @realDonaldTrump mentioning that company will appear here.'
    }
  },
  mounted () {
    axios.get('/static/twitter-data.json')
    .then((response) => {
      this.tweets = response.data
    })
  },
  methods: {
  //  show: function (x) {
  //    this.currentX = x
  }

}
</script>

<style>
#app {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 18px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 20px;
  padding:20px;
  background-color: #F5F8FA;
  /* border: thin grey solid; */
}
#drop-down-menu {
  margin-top: 2em;
  margin-left: 3.5em;
  margin-bottom: 2em;
  text-align: center;
  font-size: 25px;
}
#company-name {
  font-family: 'Mukta Vaani', sans-serif;
  font-weight: bold;
  font-size: 50px;
  float: left;
  margin-left: 2em;
  margin-top: 2em;
}
#company-logo {
  float: right;
  margin-top: 1em;
  margin-right: 1em;
}
#company-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
  margin-top: 0.1em;
}
/* Twitter Styling */
#tweet-box {
  float: left;
  margin-left: 3.5em;
  margin-top: 2em;
  margin-bottom: 2em;
}
/* Stock Chart Styling */
#stock-chart {
  float: right;
  margin-right: 2em;
  margin-top: 2em;
  margin-bottom: 2em;
}
/* Explanatory Text Box Styling */
#analysis {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
}
</style>
