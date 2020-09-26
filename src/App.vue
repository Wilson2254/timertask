<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <AddTimer @add-timer="addTimer" />
    <TimerList v-if="timers.length" v-bind:timers="timers"/>
    <p v-else>Нет тамйеров</p>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import TimerList from "./components/TimerList.vue";
import AddTimer from "./components/AddTimer.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    TimerList,
    AddTimer,
  },
  data() {
    return {
      timers: [],
    };
  },
  methods: {
    addTimer(timer) {
      this.timers.push(timer);
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
