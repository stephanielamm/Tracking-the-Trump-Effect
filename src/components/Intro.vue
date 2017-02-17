<template>
  <div class="Intro">
    <div class="header-bar"></div>
    <div class="container-fluid header-container">
    <div class="row header-title">When Trump Tweets About Public Companies</div>
    <div class="row header-about">President Donald Trump often uses Twitter to express his views on companies. His tweet's effect on a company's stock is usually brief, creating a small blip before the stock's price returns to typical levels. Some savvy investors have created computer algorithms that take advantage of the "Trump Effect," trading in the miliseconds following a tweet and resulting in huge profts. However, the long-term effect on the company's stock is typically slight.
    </div>
    <div class="row byline">By Stephanie Lamm</div>
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
.header-bar {
  background-color: #3B7B8E;
  height: 35px;
}
.header-container {
  text-align: center;
  display: block;
  margin-top: 2em;
}
.header-title {
  font-family: 'Mukta Vaani', sans-serif;
  font-size: 40px;
  font-weight: bold;
  color: #3B7B8E;
}
.header-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 18px;
  color: grey;
  margin: 0 10em 0.5em;
}
.byline {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 1.5em;
}
@media only screen and (max-width: 1275px) {
    /* For mobile phones: */
    .header-title {
      font-size: 25px;
      margin: 0px 15px 1px;
    }
    .header-about {
      font-size: 15px;
      margin: 0px 15px 1px;
    }
    .byline {
      font-size: 13px;
    }

}
</style>
