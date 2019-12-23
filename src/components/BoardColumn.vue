<template>
    <div>
        <div class="uk-card uk-card-default uk-card-body column" id="todo-col column" @click="setActiveCol(col.id)" style="cursor:pointer">
            <div class="inside-column">
                <h3> {{col.name}}</h3>
                <Task v-for="task in col.tasks" :task="task" :key="task.id" :colId="col.id" />
            </div>
        </div>
    </div>
</template>
<script>
import Task from './Task.vue';
import {store} from '../store.js';
export default {
name: 'BoardColumn',
props:['col'],
components:{
    Task
},
methods:{
    setActiveCol(colId){
     store.setActiveColumn(colId)
    }
}
}
</script>

<style scoped>
.column {
    background-color: #bae8e8;
    border-radius: 10px;
}
.inside-column {
    color: #e6b2c6;
    
}

</style>