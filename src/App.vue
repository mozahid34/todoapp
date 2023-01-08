<template>
  <div class="container">
  <img alt="Vue logo" class="logo" src="https://www.stock-app.info/media/wp-content/uploads/2022/06/ToDo-%E3%83%AA%E3%82%B9%E3%83%88-%E7%B6%9A%E3%81%8B%E3%81%AA%E3%81%84.jpg">

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
  width: 150px;
}
</style>
