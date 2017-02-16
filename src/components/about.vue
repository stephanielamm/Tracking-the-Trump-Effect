<template>
  <div class="about">
  <div class="container">
  <div class="row" id="company-about">
  <p> {{ currentAbout }}</p>
</div>
</div>
</div>
</template>
  <script>
  export default {
    props: [
      'tweets',
      'currentCompany'
    ],
    data () {
      return {
      }
    },
    computed: {
      currentCompanyData () {
        return this.tweets[this.currentCompany]
      },
      currentAbout () {
        return this.currentCompanyData.about
      }
    },
    methods: {
    }
  }
</script>
<style>
/* About company styling */
#company-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
  margin-top: 0.1em;
}
</style>
