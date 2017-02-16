<template>
<div class="stockData">
<div class="row">
<p>A chart will go here: {{ currentStockchart }}</p>
</div>
</div>
</template>

<script>
export default {
  name: 'stockData',
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
    currentStockchart () {
      if (this.currentCompanyData) return this.currentCompanyData.stockchart
    }
  },
  mounted () {
  }
}
</script>
<style>
/* Stock Chart Styling */
#stockData{
  float: right;
  margin-right: 2em;
  margin-top: 2em;
  margin-bottom: 2em;
}
</style>

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
