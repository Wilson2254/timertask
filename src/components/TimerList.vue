<template>
  <div>
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

</style>