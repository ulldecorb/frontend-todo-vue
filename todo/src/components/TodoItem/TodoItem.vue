<template>
    <li class="todo" v-bind:class="{completed: todo.completed}" key={todo.id}>
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
<style lang="css" src="./todoItem.css" scoped>
.completed {
    text-decoration: line-through;
}
</style>