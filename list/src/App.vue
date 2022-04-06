<template>
 
 <h2>Список дел</h2>
 
 <ListDeal />
 
</template>

<script>

import ListDeal from './components/ListDeal.vue'

export default {
  name: 'App',
  components: {
   ListDeal
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
