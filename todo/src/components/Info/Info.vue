<template>
    <div>
        There are {{todos.filter((todo) => !todo.completed).length}} still to do
    </div>
</template>
<script>
export default {
    name: 'Info',
    props: ['todos']    
}
</script>
<style scoped>

</style>