<template>
  <div id="app">
   <Menu />
   <Menu />
   <Menu />
   <Menu />
  </div>
</template>

<script>
import Menu from "./components/Menu.vue";

export default {
  name: "app",
  components: {
    Menu
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
