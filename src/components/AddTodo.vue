<template>
  <title-todo></title-todo>
  <div class="todo">
    <div class="todo__add__item">
      <form @submit.prevent>
        <input
            type="text"
            name="task"
            id="task"
            v-model="nameItemTodo"
            placeholder="Введите задачу">
        <button type="submit" :class="{'disabled-btn': disabledButton}" :disabled="disabledButton" @click="addTodoItem"> Добавить</button>
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
  data(){
    return {
      nameItemTodo:''
    }
  },
  computed:{
    disabledButton(){
      return !this.nameItemTodo.length
    }
  },
  methods:{
    addTodoItem() {
      this.$emit('addTodoInList', this.nameItemTodo)
      this.nameItemTodo=''
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
  cursor: pointer;
}
.disabled-btn{
  cursor: not-allowed;
  opacity: .5;
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
@media screen and (max-width: 480px) {
form{
  flex-direction: column;
  align-items: center;
}
  input{
    width: 90%;
    margin-bottom: 2rem;
  }
}
</style>
