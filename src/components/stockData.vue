<template>

<div v-show="currentCompany !== ''" class="container stockData">
<!--  <img src=" " > -->
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
.stockData {
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
</style>
