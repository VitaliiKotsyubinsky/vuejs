<template>
  <div id="app">
    <h1>Todo Application</h1>
    <hr>
    <TodoList v-bind:todos="todos" @remove-todo="removeTodo" />
  </div>
</template>

<script>

import TodoList from "@/components/TodoList"
export default {
  name: 'app',
  data() {
    return {
      todos: [
        { id: 1, title: 'Купить что-то', completed: false },
        { id: 2, title: 'Купить что-то', completed: false },
        { id: 3, title: 'Купить что-то', completed: false }
      ]
    }

  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    }

  },
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
}
</style>
