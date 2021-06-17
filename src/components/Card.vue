<template>
  <div class="movie-card">
    <img 
            
            v-if="item.poster_path != null"
            class="poster"
            :src="'https://image.tmdb.org/t/p/w342' + item.poster_path" 
            :alt="title? title:name">
    <img class="poster" v-else src="https://lh6.googleusercontent.com/proxy/oqZfItyVr9ljKfhHVg4MGubil6-uYpFbhxFQ5DrA5cLUH4KzNVq4Im2PxJxnVY07oWfBqBC6GKet7dT-m2CkuY8q7U0c6K9gkyoujcJUzR1lkrpxlC5mPIZIsm4Cfrsah4AwOGnYXUieuyR2Tfnn60k=s0-d" :alt="title? title:name">        
    <div class="card-info">
      <h3>{{ item.title }}</h3>
      <h4>original title:{{ item.original_title }} </h4>
      <span> lang: {{ item.original_language }} </span> 
      <img class="flag"  src="../assets/images/it.png" alt="" v-if="item.original_language== 'it'" >
      <img class="flag"  src="../assets/images/en.png" alt="" v-if="item.original_language== 'en'" >
      <p> {{item.overview}} </p>
      <div>
      <i 
        v-for="n in getVote()"
        :key="`full-${n}`"
        class="fas fa-star"></i>
        <i 
        v-for="n in (5 - getVote())"
        :key="`empty-${n}`"
        class="far fa-star"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: 'Card',
props: {
  "item": Object
  },
methods: {
  getVote: function(){
    return Math.ceil(this.item.vote_average/2);
  }
}  
}
</script>

<style lang="scss" >
.movie-card {
  position: relative;
  width: 324px;
  padding: 1rem;
  text-align: center;
  z-index: 0;
  h3, h4 {
    padding: .2rem;
    margin: 0;
  }
 
  .flag {
    width: 16px;
  }
}
.movie-card img{
  width: 100%;
  object-fit: contain;
}
.card-info {
  width: 100%;
  // background-color: rgba(0, 0, 0, 0.7);
  color: white;
  position: absolute;
  display: none;
  z-index: 5;
  top: 0;
  left: 0;
  height: 100%;
  h3 {
    margin-top: 2rem;
    padding: .5rem;
  };
  h4, span, {
    padding: .5rem;
  };
  p {
    padding: .8rem;
  }

}

.movie-card:hover .card-info{
  display: block;
}
.movie-card:hover .poster{
  filter: brightness(30%)
}


</style>