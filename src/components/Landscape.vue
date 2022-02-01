<template>
  <div class="window-wrapper">
    <div :style="windowStyle" class="window">
      <img :src="landscapeView" />
    </div>
  </div>
</template>
<script>
import axios from "axios";
import { pexelsApi } from "../assets/Api";
export default {
  name: "Landscape",
  props: ["wid", "hei"],
  computed: {
    windowStyle() {
      return {
        width: `${this.wid}%`,
        height: `${this.hei}%`,
      };
    },
  },
  mounted: function () {
    return axios
      .get(pexelsApi.url, {
        headers: {
          Authorization: `${pexelsApi.access_token}`,
        },
      })
      .then((res) => {
        this.landscapeView = res.data.photos[0].src.large;
      });
  },
  data() {
    return {
      landscapeView: "",
    };
  },
};
</script>
<style lang="scss" scoped>
.window-wrapper {
  background-color: rgb(53, 146, 30);
  width: 100%;
  height: 100%;
  max-width: 900px;
  max-height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}
.window {
  background: #bb4848;
  z-index: 2;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  img {
    width: 1116px;
    top: 0;
  }
}
</style>
