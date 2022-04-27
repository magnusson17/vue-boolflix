<template>
  <div id="app" class="bg_222222 h_100vh">
    <HeaderComp
      class="bg-black"
      @queryFunSon="queryFunDad"/>
    <MainComp
      class="bg_222222"
      :querySaveArrayMovies="saveApiArrayMovies"
      :querySaveArraySeries="saveApiArraySeries"/>
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
      // queryDad: 'stella',
      saveApiArrayMovies: [],
      saveApiArraySeries: [],
      // arrayConcat: []
    }
  },

  methods: {
    queryFunDad(query) {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&language=it_IT&query=${query}`).then( (res) => {
        console.log(res);
        this.saveApiArrayMovies = res.data.results;
      }),
  
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${this.apiKey}&language=it_IT&query=${query}`).then( (res) => {
        console.log(res);
        this.saveApiArraySeries = res.data.results;
      })
    }
  },
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
.bg_222222 {
  background-color: #222222;
}

.h_100vh {
  height: 100vh;
}
</style>
