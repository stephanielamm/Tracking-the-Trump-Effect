<template>
  <div class="Intro">
    <div class="header-bar"></div>
    <div class="container-fluid header-container">
    <div class="row header-title">When Trump Tweets About Public Companies</div>
    <div class="row header-about">This is a short explaination of the project. This is a short explaination of the project. This is a short explaination of the project. This is a short explaination of the project.
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
.header-bar {
  background-color: #3B7B8E;
  height: 35px;
}
.header-container {
  text-align: center;
  display: block;
  margin-top: 5em;
}
.header-title {
  font-family: 'Mukta Vaani', sans-serif;
  font-size: 50px;
  color: #3B7B8E;
}
.header-about {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  font-size: 25px;
  color: grey;
  margin: 0 2em 1.5em;
}
</style>
