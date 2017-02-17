<template>
<div class="stockData">
<div id="container"></div>
</div>
</template>

<script>
import $ from 'jquery'

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
    // currentStockchart () {
    //   if (this.currentCompanyData) return this.currentCompanyData.stockchart
    // }
  },
  mounted () {
    var Highcharts = require('highcharts/highstock')
    $(function () {
      $.get('../static/newboeing1.csv', function (stocks) {
        console.log(stocks)
        Highcharts.chart('container', {
          data: {
            data: stocks
          },
          chart: {
            type: 'line'
          },
          xAxis: {
            type: 'datetime',
            title: {
              text: 'Date'
            }
          },
          yAxis: {
            title: {
              text: 'Price'
            }
          },
          legend: {
            enabled: false
          },
          title: {
            text: 'Stock Price'
          },
          series: [{
            name: 'AAPL',
            data: stocks,
            tooltip: {
              valueDecimals: 2
            }
          }]
        })
      })
    })
  },
  methods: {
    drawChart: function () {

    }
  },
  watch: {
    currentCompanyData: function () {
      this.drawChart()
    }
  }
}
</script>
<style>
/* Stock Chart Styling */
.stockData{
  float: right;
  height: 130px;
  width: 350px;
  border: 1px solid grey;
  border-radius:5px;
  padding: 8px;
  background-color: red;
  margin: 25px 0px;
  color: black;
  font-size: 25px;
}
