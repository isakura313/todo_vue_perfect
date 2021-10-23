<template>
 <div justify="center" align="center">
  <div cols="3"> 
    <div class="todo__text">{{text}}  </div> </div>
  <div cols="4">   
  <va-button icon-right="create" class="mr-4" @click="$emit('deleteListItem')">Edit</va-button>
  </div>
 </div>
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
