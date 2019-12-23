<template>
    <div>
        <h3 align="center" class="uk-heading-divider heading ">Kanban Board</h3>
        <h2> SJ</h2>
        <p> Tutorial from Udemy, however style was updated by me</p>
        <div class="uk-grid-medium uk-child-width-expand@s uk-text-center" uk-grid>
            <!-- <BoardColumn name="Todo" />
            <BoardColumn name="InProgress" />
            <BoardColumn name="Done" /> -->
            <BoardColumn v-for="col in sharedState.Seed" :key="col.id" :col="col" />
        </div>
    </div>
</template>
<script>
import BoardColumn from './BoardColumn.vue';
import {store} from '../store.js'
export default {
  name: 'Board',
  data(){
      return {
       sharedState: store.state
      }
  },
  components:{
      BoardColumn
  }
}
</script>

<style scoped>
.heading {
    font-family: 'Inria Serif', serif;
    background-color: #f6e1e1;
    border: solid 1px;
    padding: 2% 0 2% 0;
    box-shadow: 0 0 10px rgba(0,0,0,0.5);
}

h2,p {
     font-family: 'Inria Serif', serif;
     text-align: center;
     font-size: 1em;

}
</style>