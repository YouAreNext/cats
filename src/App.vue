<template>
  <div id="app">
    <main-component/>
  </div>
</template>

<script>
import MainComponent from "./components/main.vue";

export default {
  name: "app",
  components: {
    MainComponent
  }
};
</script>

<style lang="scss">
    @import 'assets/styles/style.scss';
</style>
