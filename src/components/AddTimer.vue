<template>
  <div>
    <!-- Вызов добавления таймера -->
    <!-- Не успевал вставить иконку добавления, оставил текст -->
    <div class="AddTimer" @click="onSubmit">Add</div>
  </div>
</template>

<script>
export default {
  methods: {
    onSubmit() {
      // Создаю новый объект Таймер с айдишкой 
      const newTimer = {
        // Айдишку просто беру от даты
        id: Date.now(),
      };
      // Передаю на главный компонент
      this.$emit("add-timer", newTimer);
    },
  },
};
</script>

<style lang="scss">
.AddTimer {
  width: 225px;
  height: 120px;
  background: #696969;
   color: #9e9e9e;
  margin: 0 25px;
  margin-bottom: 45px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
</style>