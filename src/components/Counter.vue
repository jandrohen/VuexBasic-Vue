<template>
  <h1> Counter - Vuex </h1>
  <h2> Direct access: {{ $store.state.count }}</h2>
  <h2> Computed: {{ countComputed }}</h2>
  <hr>
  <button @click="increment">+1</button>
  <button @click="incrementBy5">+5</button>
  <button>Random</button>
  <hr>
  <h1>mapState</h1>
  <h2> mapState: {{ count }}</h2>
  <h2> lastMutation: {{ lastMutation }}</h2>
</template>

<script>
import { mapState } from 'vuex';

export default {

  name: 'Counter',

  computed: {
    countComputed() {
      return this.$store.state.count;
    },
    ...mapState(['count','lastMutation'])
  // ...mapState({
  //   count: state => state.count,
  //   lastMutation: state => state.lastMutation,
  // }),
  },

  methods: {
    increment() {
      this.$store.commit('increment');
    },
    incrementBy5() {
      this.$store.commit('incrementBy', 5);
    },
  }

}
</script>

<style scoped>

</style>
