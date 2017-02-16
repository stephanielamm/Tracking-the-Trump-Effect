<template>
  <div class="about">
  <div class="row" id="company-about">
  <p> {{ about }}</p>
  </div>
</div>
</template>
  <script>
  export default {
    props: [
      'tweets'
    ],
    data () {
      return {
        about: 'Text about the company will appear here.'
      }
    },
    methods: {
    }
  }
  </script>
<style>
#company-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  margin-left: 0.5em;
  margin-right: 0.5em;
  margin-top: 0.1em;
}
</style>
