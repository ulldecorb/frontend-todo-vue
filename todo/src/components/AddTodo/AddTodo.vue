<template>
    <div>
        <form class="controls__add-task-box" @submit="addTodo">
            <input type="text" v-model="newTask"
            placeholder="Add new task"
            autoComplete="off"
            maxLength="35">
          <button
            type="button"
            class="add-task-box__handle-add-button"
            data-testid="addButton"
            @click="$emit('addTodo', newTodo)"
          >
            <i class="fas fa-plus-circle fa-2x" />
          </button>
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
<style lang="css" src="./addTodo.css" scoped></style>