<template>
  <div id="app">
<Sidebar /> 
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    
  </div>
</template>

<script>

import Todos from './components/Todos';
import AddTodo from './components/AddTodo';
import Sidebar from './components/Sidebar';
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Sidebar,
    Todos,
    AddTodo
    
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      const { title, completed } = newTodo;

      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed
      })
      .then(res => this.todos = [...this.todos, res.data])
      .catch(err => console.log(err));
      
    }
  },
  created() {
  axios.get ('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(res => this.todos = res.data)
      .catch(err => console.log(err));
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 10px;
}




body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

</style>
