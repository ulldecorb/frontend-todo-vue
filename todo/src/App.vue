<template>
  <div id="app">
    <h1>Todo List</h1>
    <TodoList v-bind:todos="copyTodos" />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
// import TodoItem from './components/TodoItem.vue'

export default {
  name: 'App',
  components: {
    TodoList
  }, 
  data() {
    return {
      todos: 
    [
      {id: '1', task: 'Create VUE app', completed: true},
      {id: '2', task: 'Create todo components', completed: false},
      {id: '3', task: 'Test app', completed: false},
    ],
    copyTodos: []
    }
  },
  created(){
    this.copyTodos = [...this.todos];
  }
}
</script>

<style>
</style>
