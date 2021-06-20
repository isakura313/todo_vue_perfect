<template>
 <v-row justify="center" align="center">
  <v-col cols="3"> 
    <div class="todo__text">{{text}}  </div> </v-col>
  <v-col cols="4">   
    <v-icon class="delete_icon" @click="$emit('deleteListItem')"> mdi-delete </v-icon> </v-col>
 </v-row>
</template>

<script>

export default {
  props:{
    text: {
      type: String
    },
    key:{
      type:Number
    }
  },
  name: 'TodoItem',
}
</script>
<style scoped>
.todo__text{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  font-size:20px;
}
.delete_icon{
  width: 40px;
  height:40px;
}
.delete_icon:hover{
  cursor: pointer;
  background-color: red;
  border-radius: 50%;
  color:white
}
</style>
