<template>
<li>
    <div>
        <input type="checkbox">
        <input type="text">
        {{todo.task}}
        <button>DELETE</button>
    </div>
</li>
</template>
<script>
export default {
    name: 'TodoItem',
    props: ['todo'],
}
</script>
<style scoped>

</style>