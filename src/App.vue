<template>
  <base-container title="Vuex">
    <h3>Simple state output: {{ $store.state.counter }}</h3>
    <h3>Computed state: {{ counter }}</h3>
    <button @click="addOne">Add 1</button>
  </base-container>
  <test-container />
  <new-component />
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import TestContainer from './components/TestContainer.vue';
import NewComponent from './components/NewComponent.vue';

export default {
  components: {
    BaseContainer,
    TestContainer,
    NewComponent,
  },
  computed: {
    counter() {
      return this.$store.state.counter;
    },
  },
  methods: {
    addOne() {
      this.$store.commit('increment');
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
  margin: 2rem;
}

body {
  margin: 0;
}
</style>
