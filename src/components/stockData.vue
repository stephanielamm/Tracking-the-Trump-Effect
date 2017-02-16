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

<style>
/* Stock Chart Styling */
#stock-chart {
  float: right;
  margin-right: 2em;
  margin-top: 2em;
  margin-bottom: 2em;
}
</style>
