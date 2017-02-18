<template>
<div class="analysis">
<p>{{ currentAnalysis }}</p>
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
  margin-left: 1em;
  margin-right: 1em;
  float: left;
  font-style: italic;
}
</style>
