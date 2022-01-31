<template>
    <div>
        <form class="controls__add-task-box" @submit="addTodo">
            <input type="text" v-model="newTask"
            placeholder="Add new task"
            autoComplete="off"
            maxLength="35">
        </form>
    </div>
</template>
<script>
import { uuid } from 'vue-uuid';

export default {
    name: 'AddTodo',
    data(){
        return {
            newTask: ''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();

            const newTodo = {
                id: uuid.v4(),
                task: this.newTask,
                completed: false 
            }

            this.newTask = '';
            this.$emit('add-todo', newTodo);
        }
    }
}
</script>
<style scoped></style>