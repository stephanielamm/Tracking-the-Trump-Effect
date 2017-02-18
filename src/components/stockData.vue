<template>
  <!-- Stock Chart Box will only show if a company is selected -->
<div v-show="currentCompany !== ''" class="container stockData">
 <img v-if="currentCompanyData" :src="currentCompanyData.stockchart" alt="company stockchart" class="chart">
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

  },
  watch: {
  }
}
</script>
<style>
/* Stock Chart Styling */
.stockData {
  width: 100%;
  border: 1px solid grey;
  background-color: red;
  color: black;
  font-size: 25px;
}
.img {
  position: absolute;
    margin: auto;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}
@media only screen and (max-width: 1275px) {
    .chart {
        width: 100%;
    }
  }

</style>
