<template>
  <Hangman />
</template>

<script>
import Hangman from "./components/Hangman/Hangman.vue";

export default {
  name: "App",
  components: {
    Hangman,
  },
};
</script>

<style>
#app {
  font-family: monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
