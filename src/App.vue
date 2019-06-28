<template>
  <div id="app">
    <Header/>
    <TodoList/>
  </div>
</template>

<script>
import Header from "./components/shared/Header";
import TodoList from "./components/TodoList";

export default {
  name: "app",
  components: {
    TodoList,
    Header
  }
};
</script>

<style>
#app {
  max-width: 20%;
  min-width: 20%;
  margin-left: 40%;
  margin-right: 20%;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
