<template>
  <div class="Intro">
    <div id="header-bar"></div>
    <div class="container" id="header-container">
    <div class="row" id="header-title">When Trump Tweets About Public Companies</div>
    <div class="row" id="header-about">This is a short explaination of the project. This is a short explaination of the project. This is a short explaination of the project. This is a short explaination of the project.
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
<style scoped>
#header-bar {
  background-color: #3B7B8E;
  height: 35px;
}
#header-container {
  text-align: center;
  display: block;
  margin-top: 5em;
}
#header-title {
  font-family: 'Mukta Vaani', sans-serif;
  font-size: 50px;
  color: #3B7B8E;
}
#header-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 22px;
  color: grey;
}
</style>
