<template>
<div class="stockData">
<p>A chart will go here: {{ currentStockchart }}</p>
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
.stockData{
  float: right;
  height: 230px;
  width: 500px;
  border: 1px solid grey;
  border-radius:5px;
  padding: 8px;
  background-color: red;
  margin: 25px 0px;
  color: black;
  font-size: 25px;
}
