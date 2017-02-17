<template>
<div class="stockData">
<div id="container">
</div>
</div>
</template>

<script>
// import $ from 'jquery'

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
  },
  methods: {
    //   function drawChart () {
    //         var data = new google.visualization.DataTable();
    //         data.addColumn('string', 'Date');
    //         data.addColumn('number', 'Price');
    //         data.addRows([
    //  ['Nov 30, 2016', 150.559998],
    //  ['Dec 1, 2016', 152.389999]
    //         ]);
    //
    //         var options = {
    //           hAxis: {
    //             title: 'Date',
    //             textStyle: {
    //               color: '#01579b',
    //               fontSize: 15,
    //               fontName: 'Arial',
    //               bold: false,
    //               italic: true
    //             },
    //             titleTextStyle: {
    //               color: '#01579b',
    //               fontSize: 16,
    //               fontName: 'Arial',
    //               bold: false,
    //               italic: true
    //             }
    //           },
    //           vAxis: {
    //             title: 'Stock Price',
    //             textStyle: {
    //               color: '#1a237e',
    //               fontSize: 15,
    //               bold: false
    //             },
    //             titleTextStyle: {
    //               color: '#1a237e',
    //               fontSize: 15,
    //               bold: false
    //             }
    //           },
    //           colors: ['#a52714', '#097138']
    //         };
    //         var chart = new google.visualization.LineChart(document.getElementById('chart_div'));
    //         chart.draw(data, options);
    //       }
    // }
  },
  watch: {
  //  currentCompanyData: function () {
  //    this.drawChart()
  //  }
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

/*
var Highcharts = require('highcharts/highstock')
window.$(function () {
  window.$.get('/static/newboeing1.csv', function (csv) {
    console.log(csv)
    Highcharts.chart('container', {
      data: {
        data: csv
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
        data: csv,
        tooltip: {
          valueDecimals: 2
        }
      }]
    })
  })
})
*/
