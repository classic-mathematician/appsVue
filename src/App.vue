<!-- vi este tutorial aquí: https://www.youtube.com/watch?v=Wy9q22isx3U -->
<!-- Eduardo Vega -->


<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>    
    <img alt="jinx logo" src="./assets/jinx.png">
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo'; 


export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "League of legends",
          completed: false
        },
        {
          id: 2,
          title: "Reading",
          completed: false
        },
        {
          id: 3,  
          title: "Mathematics",
          completed: false
        }
        
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }

}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4; 
  }


</style>
