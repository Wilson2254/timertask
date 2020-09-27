<template>
  <!-- Тут у меня все таймеры -->
  <div class="List">
    <TimerItem v-for="timer in timers" :key="timer.id" />
  </div>
</template>

<script>
import TimerItem from "@/components/TimerItem.vue";
export default {
  // Основной массив в App
  props: ["timers"],
  components: {
    TimerItem,
  },
};
</script>

<style lang="scss">
// Тут я располагаю таймеры в строчку
.List {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
}
</style>