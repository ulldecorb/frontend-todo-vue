<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="newTask">
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