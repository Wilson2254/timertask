<template>
<div>
    <button @click="onSubmit">Добавить</button>
</div>
</template>

<script>
export default {
  methods:{
    onSubmit(){
        const newTimer = {
          id: Date.now(),
        }
        this.$emit('add-timer', newTimer)
      }
    }
  }
</script>