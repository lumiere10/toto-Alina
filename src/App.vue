<template>
  <AddTodo
      @addTodoInList="addTodo"
  />
<list-todo :list="list"/>

</template>

<script>

import AddTodo from './components/AddTodo.vue';
import ListTodo from './components/ListTodo.vue';
// import ItemListTodo from "@/components/ItemListTodo";
export default {
  name: 'App',
  components: {
    AddTodo,
    ListTodo
  },
  data(){
    return{
      list: [
        {id: 1, date: '04.07.2022 17:45:34', title: 'buy bread', numbers: '34556'},
        {id: 2, date: '04.07.2022 17:55:35', title: 'buy milk', numbers: '12344'},
        {id: 3, date: '04.07.2022 17:55:35', title: 'buy milk', numbers: '12344'},
        {id: 4, date: '04.07.2022 17:55:35', title: 'buy milk', numbers: '12344'},
        {id: 5, date: '04.07.2022 17:55:35', title: 'buy milk', numbers: '12344'},
        {id: 6, date: '04.07.2022 17:55:35', title: 'buy milk', numbers: '12344'},
      ],
    }
  },
  methods:{
    getIdNewItem(){
      return this.list.length ? this.list[this.list?.length-1].id + 1 : 1
    },
    formattedDate(){
      let today = new Date();
      let dd = today.getDate();
      let mm = today.getMonth() + 1;
      let yyyy = today.getFullYear();
      if (dd < 10) {
        dd = '0' + dd;
      }
      if (mm < 10) {
        mm = '0' + mm;
      }
      let time = today.toLocaleTimeString()
      today = dd + '.' + mm + '.' + yyyy
       return  `${today} ${time}`;

    },
    addTodo(newItemTodo) {
      let pattern = /\d+/g;
      let numbers = newItemTodo.match(pattern)
      const newTask = {
        id: this.getIdNewItem(),
        date: this.formattedDate(),
        title: newItemTodo,
        numbers: numbers.join(' ')
      }
      console.log(newItemTodo);
      this.list.push(newTask);
    },
    removeItem(id) {
      console.log(id, "id");
      this.list = this.list.filter(item => item.id !== id)
    },

  }
}
</script>

<style>
#app {
  font-family:  Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  font-size: 2px;

}
html{
  font-size: 16px;
}

@media screen and (max-width: 1400px) {
  html{
    font-size: 16px;
  }

  @media screen and (max-width: 480px) {
  html{
    font-size: 14px;
  }
}
}
</style>
