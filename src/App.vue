<template>
  <div id="app">
    <HeaderComp/>
  </div>
</template>

<script>
import "bootstrap"
import HeaderComp from './components/HeaderComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
  },

  data() {
    return {
      api_key: '',
    }
  }

  // created: {
  //   axios.get("https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+fut
  //   uro")
  // }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";

</style>
