<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from "../components/Todos"
import AddTodo from "../components/AddTodo"
// import VideoBg from 'vue-videobg'

export default {
  name: "home",
  components: {
    Todos,
    AddTodo,
    
  },

  data() {
    return {
      todos: []
    };
  },
  watch: {
    todos: {
      handler() {
        
        localStorage.setItem("todos", JSON.stringify(this.todos));
      },
      deep: true
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  },
  mounted() {
    
    if (localStorage.getItem("todos"))
      this.todos = JSON.parse(localStorage.getItem("todos"));
  }
};
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
