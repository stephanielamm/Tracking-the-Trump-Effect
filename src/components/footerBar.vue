<template>
<div class="container-fluid footerBar footer-container">
  <div class="row">
  <div class="col-lg-4 footer-name">A Project for the University of North Carolina by Stephanie Lamm. </div>
  <div class="col-lg-4 footer-datasource">Stock data from Yahoo Finance. Tweets from @realDonaldTrump.</div>
  <div class="col-lg-4 footer-codesource"> Stock charts made using Highstock API./div>
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
/* Footer Styling */
.footer-container {
  height: 35px;
  font-size: 13px;
  background-color: #3B7B8E;
  color: #F5F8FA;
}
.footer-name {
  float: left;
  margin-top: 5px;
}
.footer-datasource {
  margin-top: 5px;
}
.footer-codesource {
  margin-top: 5px;
  float: right;
}
</style>
