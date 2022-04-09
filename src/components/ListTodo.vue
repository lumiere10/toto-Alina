<template>
    <ul>
        <item-list-todo
        :list-item="list"
        @remove="removeItem"
        />
      <li class="info" v-if="checkListLength">Нет записей!!!</li>
    </ul>
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
  methods: {
    removeItem(id) {
      this.$emit('remove', id);


    },
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
  max-height: 35vw;
  overflow: auto;
}
.info {
  margin: 0;
  font-size: 2rem;
  text-transform: uppercase;
  color: #919191;
  list-style-type: none;
}
@media screen and (max-width: 480px) {
  ul{
    max-height: 130vw;
  }
}
</style>
