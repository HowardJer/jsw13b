<template>
  <div id="app">
    <vue-tweet-container></vue-tweet-container>
  </div>
</template>

<script>
import VueTweetContainer from "./components/TweetContainer.vue";

export default {
  name: "app",
  components: {
    VueTweetContainer,
  },
};
</script>

<style scoped>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
