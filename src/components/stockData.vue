<template>
  <!-- Stock Chart Box will only show if a company is selected -->
<div v-show="currentCompany !== ''" class="container stockData">
  <!-- Img Source comes from the stockchart value of the selected company -->
  <!-- Request for data will only be made if a company is selected  -->
 <img v-if="currentCompanyData" :src="currentCompanyData.stockchart" alt="company stockchart" class="chart img-responsive">
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
  },
  mounted () {
  },
  methods: {

  }
}
</script>
<style>
/* Stock Chart Styling */
.stockData {
  width: 100%;
  background-color: white;
  text-align: center;
  border-radius: 3px;
}
.stockData img {
  display: inline;
}
@media only screen and (max-width: 1275px) {
    .chart {
        width: 100%;
    }
  }
</style>
