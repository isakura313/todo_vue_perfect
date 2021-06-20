<template>
<v-container fluid  class="todo__wrapper">
  <todo-item  v-for="item in messages" 
    :text="item.text" 
    :key="item.key"
    @deleteListItem="$emit('deleteAppItem', item.key)"
    />
</v-container>
</template>

<script>
import TodoItem from '../components/TodoItem.vue'
export default {
  props:{
    messages:{
      type: Array,
    }
  }, 
  name: 'TodoList',
  components:{
    TodoItem
  },

}
</script>
<style scoped>

</style>

<!-- Add "scoped" attribute to limit CSS to this component only -->
