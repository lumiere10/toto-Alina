<template>
  <title-todo></title-todo>
  <div class="todo">
    <div class="todo__add__item">
      <form @submit.prevent="addTodo">
        <input type="text" name="task" id="task" v-model="newTodo">
        <button type="submit"> Добавить</button>
      </form>
    </div>
  </div>
</template>

<script>

import TitleTodo from "@/components/TitleTodo";
export default {
  name: 'AddTodo',
  components: {
    TitleTodo
  },
  props: {
    msg: String
  },
  date(){
    return {
      newTodo: ''
    }
  },
  methods:{
    addTodo() {
      this.$emit('AddTodo', this.newTodo)
      console.log

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
