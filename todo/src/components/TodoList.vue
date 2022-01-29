<template>
<div>
  <ol v-bind:key="todo.id" v-for="todo in todos">
    <li>{{todo.task}}</li>
  </ol>
</div>
</template>

<script>
export default {
  name: 'TodoList',
  props: ['todos'],
}
</script>

<style></style>
