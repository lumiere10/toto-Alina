<template>
  <li class="todo__item" v-for="todo in list" v-bind:key="todo.id">
    <div class="todo__item__id">{{todo.id}}</div>
    <div class="todo__item__date">{{todo.date}}</div>
    <div class="todo__item__text">{{todo.title}}</div>
    <div class="todo__item__numbers_from_text">{{todo.numbers}}</div>
    <button name="remove" type="submit" @click="removeTodoItem">удалить</button>
  </li>
</template>

<script>
// let id=3
export default {
  name: 'ItemListTodo',
  data(){
    return{
      list: [
        {id: 1, date: '04.07.2022 17:45:34', title: 'buy bread', numbers: '34556'},
        {id: 2, date: '04.07.2022 17:55:35', title: 'buy milk', numbers: '12344'},
      ]
    }
  },

  methods: {
    // AddTodo(newTodo){
    //   this.list.push({ id: id++, date: Date.now(), title: newTodo, numbers: newTodo})
    //   console.log( this.list)
    // },
    removeTodoItem() {
      // console.log(this)
      this.$emit('remove', this.list.id);
    },

  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
