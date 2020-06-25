<template>
  <div id="app">
    <Container />
    <List />
  </div>
</template>

<script>
import Container from "./components/Container.vue";
import List from "./components/List.vue";

export default {
  name: "App",
  components: {
    Container,
    List
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  width: 100%;
  align-items: center;
}
</style>
