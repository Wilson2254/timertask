<template>
  <div>
    <div class="AddTimer" @click="onSubmit">Add</div>
  </div>
</template>

<script>
export default {
  methods: {
    onSubmit() {
      const newTimer = {
        id: Date.now(),
      };
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
  margin: 0 25px;
  margin-bottom: 45px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>