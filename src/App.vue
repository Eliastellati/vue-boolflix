<template>
  <div id="app">
    <Header @search="searchMovie" />
    <Main :movieCards="movies"
          :serieCards="series"
    key=""/>
  </div>
</template>

<script>
import axios from 'axios';
import Main from './components/Main.vue';
import Header from './components/Header.vue';
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: function() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      movies: [],
      series: [],
      apiKey: '429b2aa1db0d31a66ad2290d9c49582f'
    }
  },
  methods: {
    searchMovie: function(text) {

      const paramsObj = {
        params: {
          api_key: this.apiKey,
          query: text,
          lang: 'it-IT'
        }
      }
      axios
      .get(this.apiUrl +'movie', paramsObj)
      .then(res=>{
        this.movies = res.data.results
      });

      axios
      .get(this.apiUrl +'tv', paramsObj)
      .then(res=>{
        this.series = res.data.results
      })
    }
  }
}
</script>

<style lang="scss">

</style>
