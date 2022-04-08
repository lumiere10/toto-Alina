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
    },
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
  display: flex;
  margin: 40px 0 0;
  align-items: end;
  justify-content: center;
}
button {
  padding: 0;
  border: none;
  background: none;
  color: #a092d2;
  text-transform: uppercase;
  font-weight: 600;
  font-size: 1.5rem;
}
input {
  display: inline-block;
  margin: 0 10px;
  padding: 0;
  border: none;
  border-bottom: 2px solid;
  border-color: #a092d2;
  width: 30%;
  font-size: 2rem;
}
input:focus{
  outline: none;
}
</style>
