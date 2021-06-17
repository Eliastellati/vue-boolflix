<template>
  <main>
      <h2> Cerca il tuo film preferito</h2>
      <div class="movie-container">
          <Card 
          v-for="card in movieCards"
          :key="card.id"
          :item="card"
          />
      </div>
      <div class="serie-container">
          <Card 
          v-for="serie in serieCards"
          :key="serie.id"
          :item="serie"
          />
      </div>
  </main>
</template>

<script>
import Card from './Card.vue';
export default {
name: 'Main',
props: ['movieCards', 'serieCards'] ,
components: {
    Card
}

}
</script>

<style>
main {
    background-color: rgb(20, 20, 20);
}
.movie-container, .serie-container {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    flex-wrap: wrap;
    margin: 0 auto;

}
h2 {
    color: white;
    padding: 3rem;
}
</style>