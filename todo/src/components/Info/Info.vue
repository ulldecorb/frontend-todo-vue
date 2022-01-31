<template>
    <span v-if="pendentTodos === 0 && totalTodos > 0">
        Good Job!
    </span>
    <span v-else-if="pendentTodos > 0">
        There are {{pendentTodos}} tasks to do
    </span>    
    <span v-else>
        Start your list!
    </span>
</template>
<script>
export default {
    name: 'Info',
    props: ['todos'],
    data(){
        return {
            pendentTodos: 0,
            totalTodos: 0
        }
    },
    created(){
        this.pendentTodos = this.todos.filter((todo => !todo.completed)).length;
        this.totalTodos = this.todos.length;
    }
}
</script>
<style lang="css" src="./info.css" scoped>

</style>