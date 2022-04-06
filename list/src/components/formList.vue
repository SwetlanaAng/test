<template>
  <div class="form">
  <form @submit.prevent="createNewDeal">
    <label for="title">Добавьте в список новое значение:</label><br>
    <input type="text" id="title" placeholder="Введите текст" v-model="newDeal">
    
    <button>Добавить дело</button>
  </form>
  </div>
    
</template>

<script>
export default {
  name: 'formList',
  data() {
      return {
        newDeal: ''
      }
   },
  methods: {
    createNewDeal() {
      if(this.newDeal) {
        this.$emit('add-deal', this.newDeal);
        this.newDeal = '';
      }
  }
}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
input{
margin: 20px;
padding: 10px;
border: 1px solid rgb(196, 196, 196);
border-radius: 3px;}
button{
padding: 10px;
border: 1px solid black;
border-radius: 3px;
background-color: black;
color: aliceblue;
margin-bottom: 20px;
}
button:hover{
background-color: rgb(201, 202, 202);
color: black;}
</style>
