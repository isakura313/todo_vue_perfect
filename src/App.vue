<template>
    <div>
      <div class="row">
        <div class="flex md12">
           <va-input
            class="mb-4"
            v-model="newTodo"  
            @keypress.enter="addDeal" 
            placeholder="Создайте дело"/>
            <va-button @click="addDeal"> Add </va-button>
           </div>
          </div>
           <TodoList :messages="todos"  @deleteAppItem = "deleteItem"/>
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
    todos: [],
  }),
  methods: {
    addDeal() {
      if(this.newTodo == ''){
        return
      }
      this.todos.push({ key: +new Date(), text: this.newTodo });
      this.newTodo = '';
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
</style>