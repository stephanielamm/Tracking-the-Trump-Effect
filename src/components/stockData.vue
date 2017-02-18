<template>
  <!-- Stock Chart Box will only show if a company is selected -->
<div v-show="currentCompany !== ''" class="container stockData">
 <img :src="currentCompanyData.stockchart" alt="company stockchart" style="width:100px;height:100px;"/>
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
    currentCompanyData () {
      return this.tweets[this.currentCompany]
    },
    currentLogo () {
      if (this.currentCompanyData) return this.currentCompanyData.stockchart
    }
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
  height: 100px;
  width: 100px;
  border: 1px solid grey;
  border-radius:5px;
  padding: 8px;
  background-color: red;
  margin: 25px 0px;
  color: black;
  font-size: 25px;
}
</style>
