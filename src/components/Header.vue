<template>
  <header>
      <a href="#">
          <img src="" alt="">
      </a>
      <div>
          <input v-model="searchText"
          type="text" placeholder="Cerca un Film">
          <button @click="$emit('search', searchText)" >Cerca</button>
      </div>
  </header>
</template>

<script>
export default {
name: 'Header',
data: function(){
    return {
        searchText: ''
    }
}
}
</script>

<style>
header {
    display: flex;
    justify-content: space-between;
    padding: 10px 15px;
}
</style>