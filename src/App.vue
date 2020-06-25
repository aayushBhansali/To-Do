<template>
  <div id="app" class="background">
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
.background {
  background: url("../src/assets/background.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ccc;
  background: rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  width: 100%;
  align-items: center;
  height: 100%;
}
</style>
