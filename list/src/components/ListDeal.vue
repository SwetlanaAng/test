<template>
  <formList v-on:add-deal="createNewDeal" />
  
    <div v-for="deal in list" :key="deal.id">
      
      <span>{{ deal.text }}</span>
      <button @click="deleteNewDeal(deal.id)">Удалить</button>
    </div>
 

  
</template>

<script>
import formList from './formList';

export default {
  name: 'ListDeal',
  components: { formList },
  data() {
    return {
      list: []
    }
  },
  methods: {
    deleteNewDeal(id) {
      let newArr = [];
      this.list.forEach(item => {
          if(item.id !=id)
           newArr.push(item);
      });
      this.list = newArr;
    },
    createNewDeal(newDeal) {
      this.list.push({id: this.list.length+1, text: newDeal });
    }
  }
}
</script>

<style>
span {
margin-right: 30px;}
/*



form {
  float: right;
  width: 15%;
  padding: 35px;
}

form > * {display: block}
form > label {margin: 7px 0}
form > input, form > textarea {
  border: 1px solid silver;
  border-radius: 5px;
  font-size: 14px;
  padding: 10px;
  resize: none;
}

form > textarea {height: 100px}

form > button {
  border: 0;
  background: #E06249;
  border-radius: 5px;
  color: #fff;
  font-weight: bold;
  padding: 10px;
  cursor: pointer;
  outline: none;
  margin-top: 15px;
  transition: transform 600ms ease;
}

form > button:hover {
  transform: translateY(-5px);
}

form > label > span {
  color: #E06249;
  font-weight: bold;
  display: block;
  margin: 5px 0;
}

form.error > label[for='text'] {color: #E06249}
form.error > textarea {border-color: #E06249}*/
</style>
