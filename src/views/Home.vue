<template>
  <div class="home">
    <main-calculation msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src

import MainCalculation from "../components/MainCalculation.vue";

export default {
  name: "Home",
  components: {
    MainCalculation,
  },
};
</script>

MainCalculation
