<template>
  <div class="dropDown">
    <!-- Dropdown menu to set company -->
    <p id="drop-down-menu">Company:
    <select v-model="currentCompany" class="company">
      <option value="The Trump Effect">Select a Company</option>
      <option value="Boeing">Boeing</option>
      <option value="Fiat-Chrysler">Fiat-Chrysler</option>
      <option value="Ford">Ford</option>
      <option value="Toyota">Toyota</option>
      <option value="Nordstrom">Nordstrom</option>
      <option value="Rexnord">Rexnord</option>
      <option value="United Technologies">United Technologies</option>
      <option value="General Motors">General Motors</option>
    </select>
  </br>
    <div class="container company-container">
      <div class="row company-name">
        <div class="col-12">{{ currentCompany }}</div>
        </div>
    </div>
  <about :currentCompany="currentCompany" :tweets="tweets"></about>
</div>

</template>

<script>
import about from '../components/about'
export default {
  props: [
    'tweets'
  ],
  data () {
    return {
      currentCompany: 'The Trump Effect'
    }
  },
  methods: {
  },
  components: {
    about
  }
}
</script>
<style>
#app {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
#drop-down-menu {
  margin: 0.5em 4em 3em 0.5em;
  text-align: center;
  font-size: 25px;
}
.company-container {
  background-color: #F5F8FA;
  width: 85%;
  height:100px;

}
.company-name {
  padding: 1em 3em 3em 1em;
  font-family: 'Mukta Vaani', sans-serif;
  font-weight: bold;
  font-size: 40px;
}

</style>
