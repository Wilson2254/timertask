<template>
  <div class="List">
    <TimerItem 
    v-for="timer in timers"
    :key="timer.id"
    />
  </div>
</template>

<script>
import TimerItem from "@/components/TimerItem.vue";
export default {
  props: ['timers'],
  components: {
    TimerItem,
  },
};
</script>

<style lang="scss">
  .List{
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
  }
</style>