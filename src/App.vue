<template>
  <div id="app">
    <TimerList v-bind:timers="timers"/>
    <AddTimer @add-timer="addTimer" />
  </div>
</template>
<script>

import TimerList from "./components/TimerList.vue";
import AddTimer from "./components/AddTimer.vue";

export default {
  name: "App",
  components: {

    TimerList,
    AddTimer,
  },
  data() {
    return {
      timers: [Object],
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
  font-family: 'Gotham Pro Regular';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-wrap: wrap;
}
@font-face {
font-family: 'Gotham Pro Regular';
src: url('GothamPro.eot');
src: url('GothamPro.eot?#iefix') format('embedded-opentype'),
url('GothamPro.woff') format('woff'),
url('GothamPro.ttf') format('truetype');
font-weight: normal;
font-style: normal;
}
</style>
