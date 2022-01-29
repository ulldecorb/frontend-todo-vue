<template>
<div>
  <ol v-bind:key="todo.id" v-for="todo in todos">
    <TodoItem v-bind:todo="todo" />
  </ol>
</div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  name: 'TodoList',
  props: ['todos'],
  components: {TodoItem}
}
</script>

<style scoped></style>
