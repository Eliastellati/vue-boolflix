<template>
  <main>
      <h2 v-if="cards.lenght=0" > Cerca il tuo film preferito</h2>
      <div class="movie-container">
          <Card 
          v-for="card in cards"
          :key="card.id"
          :item="card"
          />
      </div>
  </main>
</template>

<script>
import Card from './Card.vue';
export default {
name: 'Main',
props: ['cards'],
components: {
    Card
}

}
</script>

<style>
.movie-container {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    flex-wrap: wrap;
    margin: 0 auto;

}
</style>