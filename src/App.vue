<template>
  <div>
    <counter></counter>
    <div>
      <h2>App vue Counter</h2>
      <!-- {{ $store.state.count }} -->
      <!-- or computed property also same -->
      {{ count }}
    </div>
    <div>
      <button @click.prevent="onIncrement()">Increment</button>
    </div>
    <div>
      <todoslist></todoslist>
    </div>
    <div>
      Todos list complete:{{  doneListCount}}
    </div>
  </div>
  
</template>

<script>
import Counter from './components/Counter.vue'
import Todoslist from './components/Todoslist.vue'

export default {
  name: 'App-Vuex',
  // or 
  computed:{
    count(){
      // 1. state
      return this.$store.state.count; 
    },
    doneListCount() {
          return this.$store.getters.doneTodosListCount;
    }
  },
  components: {
    Counter,
    Todoslist
  },
  methods:{
    onIncrement(){ 
      this.$store.commit('increment', { value: 2});
      // or
      // this.$store.commit({
      //   type: 'increment',
      //   value: 4,
      // }),
      },
      // getDoneListCount() {
      //     return this.$store.state.todos.filter((todo) => todo.done).length;
      // }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
