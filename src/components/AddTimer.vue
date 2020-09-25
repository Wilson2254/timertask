<template>
<div>
    <button @click="onSubmit"></button>
</div>
</template>

<script>
export default {
  methods:{
    onSubmit(){

        const newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false
        }
        this.$emit('add-todo', newTodo)
        this.title = ''
      }
    }
  }
}
</script>