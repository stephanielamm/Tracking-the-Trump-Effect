<template>
  <!-- Stock Chart Box will only show if a company is selected -->
<div v-show="currentCompany !== ''" class="container stockData">
 <img v-if="currentCompanyData" :src="currentCompanyData.stockchart" alt="company stockchart">
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
  float: right;
  height: 200px;
  width: 200px;
  border: 1px solid grey;
  border-radius:5px;
  padding: 8px;
  background-color: red;
  margin: 25px 0px;
  color: black;
  font-size: 25px;
}
</style>
