<template>
  <v-app>
    <v-main>
      <v-container fluid  class="todo__wrapper">
        <v-row justify="center" align="center">
          <v-col cols="4">
           <input v-model="newTodo" class="todo__input"  @keypress.enter="addDeal" placeholder="Создайте дело"/>
          </v-col>
          <v-col cols="2">
        <v-btn @click="addDeal"> Add </v-btn></v-col>
          </v-row>
          </v-container>
              <todo-list :messages="todos"  @deleteAppItem = "deleteItem"/>
    </v-main>
  </v-app>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",

  components: {
    TodoList,
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
      console.log(+new Date());
    },
    deleteItem(key){
      console.log(key)
      this.todos = this.todos.filter(item => item.key != key)
    }
  },
};
</script>

<style>
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