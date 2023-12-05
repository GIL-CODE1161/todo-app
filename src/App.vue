<template>
  <h1 class="title">TODO APP WITH VUE JS</h1>
  <div id="app" class="container">
    <img alt="Vue logo" src="./assets/logo.png" class="logo">
    <todo-list></todo-list>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    HelloWorld,
    // eslint-disable-next-line vue/no-unused-components
    TodoList,
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
.container {
  max-width: 400px;
  margin: 0 auto;
  border: 1px solid black;
  border-radius: 60px;
  /* background-image: radial-gradient(black, white, black); */
  background-image: linear-gradient(to left, white,black, white);
  border-right-width: 10px;
  border-left-width: 10px;
  border-left-color: #65786B;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
  font-size: 18px;
}
.logo {
  display: block;
  margin: 20px auto;
  height: 75px;
}
.title {
  display: flex;
  margin-left: 350px;
}

</style>
