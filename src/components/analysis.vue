<template>
<div class="analysis">
<div class="row">
<p>Effect on the stock: {{ currentAnalysis }}</p>
</div>
</div>
</template>

<script>
export default {
  name: 'analysis',
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
    currentAnalysis () {
      if (this.currentCompanyData) return this.currentCompanyData.analysis
    }
  },
  mounted () {
  }
}
</script>

<style>
/* Explanatory Text Box Styling */
#analysis {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
}
</style>
