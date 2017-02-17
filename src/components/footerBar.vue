<template>
<div class="container-fluid footerBar footer-container">
  <p>Copyright Stephanie Lamm</p>
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
  background-color: #3B7B8E;
  color: white;
}

</style>
