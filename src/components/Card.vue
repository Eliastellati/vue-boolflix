<template>
  <div class="movie-card">
    <img 
            class="poster"
            :src="'https://image.tmdb.org/t/p/w342' + item.poster_path" 
            :alt="title? title:name">
    <h3>{{ item.title }}</h3>
    <h4>original title:{{ item.original_title }} </h4>
    <p> lang: {{ item.original_language }} </p>
    <p> {{ item.vote_average }} </p>
  </div>
</template>

<script>
export default {
name: 'Card',
props: {
  "item": Object
}    
// methods: {
//   langFlag
// } 
}
</script>

<style lang="scss" >
.movie-card {
  width: 20%;
  padding: 2%;
  text-align: center;
  h3, h4 {
    padding: .2rem;
    margin: 0;
  }
}
.movie-card img{
  width: 100%;
}

</style>