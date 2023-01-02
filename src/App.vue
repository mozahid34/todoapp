<template>
  <div class="container">
  <img alt="Vue logo" class="logo" src="./assets/logo.png">

  <todo-list></todo-list>
 
  
  
  


  
</div>
  
  
</template>

<script>
import TodoList from './components/todo-list.vue'







export default {
  name: 'App',
  components: {
    TodoList
   
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 18px;
}

.logo {
  display: block;
  margin: auto;
  width: 75px;
}
</style>
