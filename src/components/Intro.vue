<template>
  <div class="Intro">
    <div class="container-fluid header-container">
      <!-- Site Title -->
    <div class="row header-title">When Trump Tweets About Public Companies</div>
      <!-- Text about the website -->
    <div class="row header-about">President Donald Trump often uses Twitter to express his views on companies. His tweet's effect on a company's stock is usually brief, creating a small blip before the stock's price returns to typical levels. Some savvy investors have created computer algorithms that take advantage of the "Trump Effect," trading in the miliseconds following a tweet and resulting in huge profts. However, the long-term effect on the company's stock is typically slight.</br></br>
      Use this tool to learn about the companies Trump has tweeted about and what that attention has done to their stock price. Select a company to display information about the company, a Donald Trump tweet, historical price data, and an analysis of the "Trump Effect."
    </div>
    <!-- Byline and Github Link -->
    <div class="row byline">By Stephanie Lamm   <a href="https://github.com/stephanielamm"><img border="0" alt="Github" src="static/git.png" width="20" height="20"></a>
</div>
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
/* Intro Stylings */
.header-container {
  display: block;
  margin-top: 2em;
}
.header-title {
  text-align: center;
  font-family: 'Mukta Vaani', sans-serif;
  font-size: 40px;
  font-weight: bold;
  color: #3B7B8E;
}
.header-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 18px;
  color: #696969;
  margin: 0 10em 0.5em;
}
.byline {
  text-align: center;
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 1.5em;
}
  /* For mobile: */
@media only screen and (max-width: 1275px) {
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
