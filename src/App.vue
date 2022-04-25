<template>
  <div id="app">
    <HeaderComp
      @queryFunSon="queryFunDad"/>
    <MainComp
      :queryFunSecondSon="saveApiInArray"/>
  </div>
</template>

<script>
import axios from 'axios';
import "bootstrap";
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },

  data() {
    return {
      apiKey: '8394997a63098bf1d50381cfa5bc4c64',
      queryDad: 'rick',
      saveApiInArray: [],
    }
  },

  created() {
    axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&language=en-US&query=${this.queryDad}&page=1&include_adult=false`).then( (res) => {
      console.log(res);
      this.saveApiInArray = res.data.results;
    })
  },

  methods: {
    queryFunDad(query) {
      this.queryDad = query;
      console.log(this.queryDad);
    },
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";

</style>
