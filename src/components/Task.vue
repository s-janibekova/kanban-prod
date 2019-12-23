<template>
    <div class="has-text-centered icons" style="background-color: #d77fa1 ">
        <div class="uk-alert-default" style="background-color: #e3f6f5 " uk-alert>
            <p>{{task.title}}</p>
            <template v-if="task.edit">
                <input type="text" class="uk-input uk-form-width-medium uk-form-small btn-style" :placeholder="task.title" v-model="newTitle" />
                <button @click="updateTask(colId, task.id, newTitle)" class="uk-button uk-button-secondary uk-button-small btn-style" > Save</button>
            </template>
            <template v-else>
                <button class="uk-button uk-button-primary uk-button-small btn-style" @click="editTask(colId, task.id)">
                    Edit
                </button>
                <span style="margin:2px">
                </span>
                <button class="uk-button uk-button-danger uk-button-small btn-style">
                    Delete
                </button>
            </template>
        </div>
    </div>
</template>
<script>
import {store} from '../store.js';
export default {
    name: 'Task',
    props: ['task','colId'],
    data(){
        return {
            newTitle: ''
        }
    },
    methods:{
        editTask(colId, taskId){
         store.editTask(colId, taskId)
        },
        updateTask(colId, taskId, taskTitle){
            store.updateTask(colId, taskId, taskTitle)

        }
    }
}
</script>


<style scoped>
.btn-style {
    border-radius: 1em;
    margin-top: 20px;
}

</style>
