<template>
  <div>
    <div class="TimerItem">
      <div class="Timer">
        <div class="Counter">{{ hour ? `${hour}:` : `` }}{{ min ? `${min}:` : !min && hour ? `${min}:` : `` }}{{ sec }}</div>
      </div>
      <div class="Control">
        <div class="Start" v-if="!isPlay" @click="Start">Start</div>
        <div class="Stop" v-else @click="Stop">Stop</div>
        <div class="Reset" @click="Reset">Reset</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    timer: {
      type: Object,
    },
  },
  data() {
    return {
      isPlay: false,
      sec: 0,
      min: 0,
      hour: 0,
    };
  },
  methods: {
    Start() {
      this.isPlay = !this.isPlay;
      this.play = setInterval(() => {
        this.sec ++;
        if (this.sec == 60) {
          this.sec = 0;
          this.min++;
        }
        if (this.min == 60) {
          this.sec = this.min = 0;
          this.hour++;
        }
      }, 1000);
    },
    Stop() {
      this.isPlay = !this.isPlay;
      clearInterval(this.play);
    },
    Reset() {
      this.sec = this.min = this.hour = 0;
      clearInterval(this.play);
    },
  },
};
</script>

<style lang="scss">
.TimerItem {
  width: 225px;
  height: 120px;
  background: #696969;
  margin: 0 25px;
  margin-bottom: 45px;
  .Timer {
    border-bottom: 1px solid #9e9e9e;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .Control {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60px;
    .Reset {
      margin-left: 48px;
      cursor: pointer;
    }
    .Start, .Stop{
      cursor: pointer;
    }
  }
}
</style>