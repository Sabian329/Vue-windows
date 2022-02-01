<template>
  <div class="hello">
    <div class="room-wrapper">
      <Room class="room" />
      <Landscape :wid="width" :hei="height" />
    </div>
    <div class="inputs-wrapper">
      <label for="widthInput">{{ Math.round(width / 11) }}</label>
      <input name="widthInput" type="range" v-model="width" />
      <label for="heightInput">{{ height / 50 }}</label>
      <input name="heightInput" type="range" v-model="height" />
    </div>
  </div>
</template>

<script>
import Landscape from "./Landscape.vue";
import Room from "./Room.vue";
export default {
  name: "MainCalculation",
  components: { Room, Landscape },

  data() {
    return {
      width: 50,
      height: 10,
    };
  },
};
</script>
Landscape

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.room-wrapper {
  background: #a89595;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 30rem;
  .room {
    position: absolute;
    z-index: 1;
  }
}
.inputs-wrapper {
  background: red;
  bottom: 0;
  display: flex;
  label {
    width: 5rem;
  }
}
</style>
