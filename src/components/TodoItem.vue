<template>
  <div class="row"> 
    <span> {{text}} </span>
    <va-button icon-right="create" class="mr-4" @click="$emit('deleteListItem')">Edit</va-button>
  </div>
</template>

<script>
import {VaButton } from 'vuestic-ui'


export default {
  props:{
    text: {
      type: String
    },
    key:{
      type:Number
    }
  },
    components: {
      VaButton
  },
  name: 'TodoItem',
}
</script>
