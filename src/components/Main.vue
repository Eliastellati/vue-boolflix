<template>
  <main>
      <h2>Film</h2>
      <ul class="movies">
          <Card 
          :v-for="card in cards"
          :key="card.id"
          />
      </ul>
  </main>
</template>

<script>
import Card from './Card.vue';
export default {
name: 'Main',
components: {
    Card
},
props: ['cards']
}
</script>

<style>

</style>