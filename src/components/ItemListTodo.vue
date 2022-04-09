<template>
  <li class="todo__item" v-for="todo in listItem" :key="todo.id">
    <div class="todo__item__id">{{todo.id}}</div>
    <div class="todo__item__date">{{todo.date}}</div>
    <div class="todo__item__text">{{todo.title}}</div>
    <div class="todo__item__numbers_from_text">{{todo.numbers}}</div>
    <button
        name="remove"
        type="submit"
    >удалить</button>
  </li>


</template>

<script>
export default {
  name: 'ItemListTodo',
  props:{
    listItem:{
      type: Array,
      required: true
    },
  },
  methods: {


  }
}


</script>

<style scoped>

li {
  list-style-type: none;
  display: grid;
  grid-template-columns: 5% 15% 60% 10% 10%;
  padding: 1rem 2rem;
  align-items: center;
}
li:not(:last-child) {
  border-bottom: 3px solid #e8e0cf;
}

 li div{
   list-style-type: none;
   padding: 0 5px;
   font-size: 1.5rem;
}
 li button{
   background: none;
   box-shadow: none;
   border: 2px solid #a092d2;
   border-radius: 11px;
   font-size: 1.1rem;
   height: 2rem;
   display: flex;
   justify-content: center;
   align-items: center;
   padding: 0;
   line-height: 1.1;
   text-transform: uppercase;
   font-weight: 500;
   cursor: pointer;

 }
 li div.todo__item__text{
   text-align: justify;
   max-height: 3rem;
   overflow: hidden;
   text-overflow: ellipsis;
   white-space: nowrap;
 }

@media screen and (max-width: 480px) {
  li{
    grid-template-columns: 100%;
  }
  li div{
    margin-bottom: 10px;
  }
  li div.todo__item__text{
    text-align: center;
}
  }
</style>
