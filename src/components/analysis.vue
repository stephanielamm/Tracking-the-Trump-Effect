<template>
<div class="row">
<div class="col-6" id="tweet-box">
{{ tweettext }}
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
    }
  },
  methods: {
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
