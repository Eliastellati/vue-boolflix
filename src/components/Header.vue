<template>
  <header>
      <a href="#">
          <img src="../../src/assets/logo-boolflix.png" alt="">
      </a>
      <div class="search">
          <input v-model="searchText"
          type="text" placeholder="Cerca un Film"
          @keyup.enter="$emit('search', searchText)"  >
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

<style lang="scss">
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 15px;
    background-color: rgb(66, 66, 66);
}
.search {
    width: 50%;
    text-align: end;
    input {
        width: 50%;
        padding: .5rem;
    }
    button {
        padding: .5rem;
    }
}
</style>