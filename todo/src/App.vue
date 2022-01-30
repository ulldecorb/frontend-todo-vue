<template>
  <div id="app">
    <h1>Todo List</h1>
    <TodoList v-bind:todos="copyTodos" v-on:delete-task="deleteTask" />
    <Info v-bind:todos="copyTodos" />
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import TodoList from './components/TodoList/TodoList.vue'
import AddTodo from './components/AddTodo/AddTodo.vue';
import Info from './components/Info/Info.vue'

export default {
  name: 'App',
  components: {
    TodoList, AddTodo, Info
  },
  methods: {
    deleteTask(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
      this.copyTodos = [...this.todos];
    },
    addTodo(todo){
      this.todos = [...this.todos, todo];
      this.copyTodos = [...this.todos];
    }
  },
  data() {
    return {
      todos: 
    [
      {
        id: '5889190e-d1e0-41c1-8f70-4a5f0ba019b7', 
        task: 'Create VUE app', 
        completed: true},
      {
        id: 'e5dd43e5-e297-4bfe-9fe7-1a28919115c4', 
        task: 'Create todo components', 
        completed: false},
      {
        id: '68623699-6cdf-405b-af75-27ab367e171b', 
        task: 'Test app', 
        completed: false},
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
