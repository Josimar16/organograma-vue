<template>
  <div id="app">
    <Organograma />
  </div>
</template>

<script>
import Organograma from "./components/Organograma.vue";

export default {
  name: "App",
  components: {
    Organograma,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
