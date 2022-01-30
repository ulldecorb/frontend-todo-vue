<template>
<li class="todo" v-bind:class="{completed: todo.completed}">
        <input type="checkbox" 
        v-bind:checked="todo.completed ? 'checked' : ''"
        v-on:change="checkTodo">
        <input type="text" v-bind:value="todo.task">
        {{todo.task}}
        <button @click="$emit('delete-task', todo.id)">DELETE</button>
</li>
</template>
<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
      checkTodo() {
          this.todo.completed = !this.todo.completed;
      }
  }
}
</script>
<style scoped>
.completed {
    text-decoration: line-through;
}
</style>