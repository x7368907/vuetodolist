<template>
  <div id="app" class="container">
    <h1>Vue TodoList</h1>
    
    <TodoInput /> 
    <TodoList />
    <TodoStatus />
  </div>
</template>

<script>
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
import TodoStatus from "./components/TodoStatus.vue";
export default {
  name: "App",
  components: {
    TodoInput,
    TodoList,
    TodoStatus
  }
};
</script>

<style>
body{
  background-color: rgb(206, 138, 206);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 3rem;
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  background-color: rgb(224, 190, 224);
}

h1{
  text-align: center;
  color: #FFF;
}
</style>




