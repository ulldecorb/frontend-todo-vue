<template>
<div>
  <ol class="list__box" v-bind:key="todo.id" v-for="todo in todos">
    <TodoItem v-bind:todo="todo" v-on:delete-task="$emit('delete-task', todo.id)"/>
  </ol>
</div>
</template>

<script>
import TodoItem from '../TodoItem/TodoItem.vue';

export default {
  name: 'TodoList',
  props: ['todos'],
  components: { TodoItem }
}
</script>

<style lang="css" src="./todolist.css" scoped></style>
