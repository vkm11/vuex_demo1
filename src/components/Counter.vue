<template>
  <div>
      <!-- <div>{{ $store.state.count }}</div> -->
      <!-- or -->
      <div> {{count}}</div>
      <div>
          <button @click.prevent="onIncrement()">Increment</button>
      </div>
  </div>
</template>

<script>
export default {
    name: "vuex-state",
    data(){
        return{};
    },
    // or
    computed:{
        count(){
            return this.$store.state.count;
        }
    },
    methods:{
        onIncrement(){
            // State:-
            // this.$store.state.count++;
            
            // Mutation:-
            this.$store.commit('increment',{value:3})
            // or
            // this.$store.commit({
            //     type: 'increment',
            //     value: 4,
            // })
        }
    }
};
</script>

<style>

</style>