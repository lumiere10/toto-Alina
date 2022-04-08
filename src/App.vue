<template>
  <AddTodo></AddTodo>
  <list-todo></list-todo>
</template>

<script>
import AddTodo from './components/AddTodo.vue';
import ListTodo from './components/ListTodo.vue';

export default {
  name: 'App',
  components: {
    AddTodo,
    ListTodo
  },
  // props:{
  //   list:{
  //     type: Array,
  //     required: true
  //   }
  // },
  methods:{

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
