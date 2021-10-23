<template>
  <div>
    <div>
      <div fluid  class="todo__wrapper">
        <div justify="center" align="center">
          <div cols="4">
           <va-input 
           v-model="newTodo"  
           class="mb-4" 
           @keypress.enter="addDeal" 
           placeholder="Создайте дело"/>
          </div>
          <div cols="2">
          <va-button @click="addDeal"> Add </va-button></div>
          </div>
          </div>
        <todo-list :messages="todos"  @deleteAppItem = "deleteItem"/>
    </div>
  </div>
</template>

<script>
import { VaInput, VaButton } from 'vuestic-ui'

import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    TodoList,
    VaInput,
    VaButton
  },

  data: () => ({
    newTodo: "",
    todos: [
      {
        key: 1,
        text: "Первое дело",
      },
    ],
  }),
  methods: {
    addDeal() {
      this.todos.push({ key: +new Date(), text: this.newTodo });
    },
    deleteItem(key){
      this.todos = this.todos.filter(item => item.key != key)
    }
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@0,400;1,700&display=swap');
@import url('https://fonts.googleapis.com/icon?family=Material+Icons');
.todo__wrapper {
  width: 800px;
  border-right: 2px solid black;
}
.todo__input{
  padding: 5px;
  margin-right: 20px;
  font-size: 20px;
}
</style>