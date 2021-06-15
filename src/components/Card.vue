<template>
  <li>
    <h3>{{ item.title }}</h3>
    <h4>{{ item.original_title }} </h4>
    <p> {{ item.original_language }} </p>
    <p> {{ item.vote_average }} </p>
  </li>
</template>

<script>
export default {
name: 'Card',
props: {
  "item": Object
}
}
</script>

<style>

</style>