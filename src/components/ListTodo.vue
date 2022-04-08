<template>
    <ul>
        <item-list-todo
            v-on:remove="removeFromList" v-model="removeFromList" > </item-list-todo>
    </ul>
  <h3>Нет записей!!!</h3>
</template>

<script>
import ItemListTodo from "@/components/ItemListTodo";
export default {
  name: 'ListTodo',
  components: {ItemListTodo},
  props:{
    list:{
      type: Array,
      required: true
    }
  },

  methods:{

    removeFromList(id) {
      console.log(this)
      this.todo = this.list.filter(item => item.id !== id)

    }
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
