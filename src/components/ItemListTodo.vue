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


li {
  list-style-type: none;
  display: grid;
  grid-template-columns: 5% 15% auto auto 10%;
  padding: 20px 40px;

}
li:not(:last-child) {
  border-bottom: 3px solid #e8e0cf;
}

 li div{
   list-style-type: none;
   padding: 0;
   font-size: 1.5rem;
}
 li button{
   background: none;
   box-shadow: none;
   border: 2px solid #a092d2;
   border-radius: 11px;
   font-size: 1.1rem;
   display: flex;
   justify-content: center;
   align-items: center;
   padding: 0;
   line-height: 1.1;
   text-transform: uppercase;
   font-weight: 500;
 }
</style>
