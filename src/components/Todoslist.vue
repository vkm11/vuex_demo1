<template>
  <div style="text-align: left">
    <h2>Todos List (Done: {{ doneListCount}})</h2>
      <ul>
          <li v-for="todo in todosList" :key="todo.id">
            {{todo.text}} - ({{todo.done ? 'Done' : 'Not Done'}})
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name:"todos-List",
    data(){
        return{};
    },
    computed:{
        todosList(){
            return this.$store.state.todos;
        },
        doneListCount(){
            return this.$store.getters.doneTodosListCount;
        }
    },
    methods:{
        // getDoneListCount(){
        //     return this.todosList.filter((todo) => todo.done).length;
        // },
    }
};
</script>

<style>

</style>