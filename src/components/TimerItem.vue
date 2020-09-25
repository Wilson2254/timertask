<template>
  <div>
    <div class="TimerItem">
      <div class="Timer">
        <div class="Counter">Count</div>
      </div>
      <div class="Control">
        <div class="Play" v-if="!isPlay" @click="isPlay = !isPlay">Play</div>
        <div class="Play" v-else @click="isPlay = !isPlay">Stop</div>
        <div class="Stop">Reset</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPlay: false,
    };
  },
};
</script>

<style lang="scss">
.TimerItem {
  width: 225px;
  height: 120px;
  background: #696969;
  .Timer {
    border-bottom: 1px solid #9e9e9e;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .Control {
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60px;
    .Stop {
      margin-left: 48px;
    }
  }
}
</style>