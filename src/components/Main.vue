<template>
  <main>
      <h2 v-if="cards.lenght=0" > Cerca il tuo film preferito</h2>
      <ul class="movies">
          <Card 
          v-for="card in cards"
          :key="card.id"
          :item="card"
          />
      </ul>
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

</style>