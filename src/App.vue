<template>
  <div id="app">
    <Header @search="searchMovie" />
    <Main :cards="movies"/>
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
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
      movies: [],
      apiKey: '429b2aa1db0d31a66ad2290d9c49582f'
    }
  },
  methods: {
    searchMovie: function(text) {
      axios
      .get(this.apiUrl, {
        params: {
          api_key: this.apiKey,
          query: text,
          lang: 'it-IT'
        }
      })
      .then(res=>{
        this.movies = res.data.results
      })
    }
  }
}
</script>

<style lang="scss">

</style>
