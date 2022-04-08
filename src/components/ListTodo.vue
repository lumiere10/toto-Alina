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

<style scoped>
ul {
  width: 90%;
  margin: 0 auto;
  border: 3px solid #e8e0cf;
  padding: 20px 0;
  margin-top: 40px;
  border-radius: 30px;
}
h3 {
  margin: 40px 0 0;
  font-size: 2rem;
  text-transform: uppercase;
  color: #919191;
}
</style>
