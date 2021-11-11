<template>
  <div class="section">
    <h2>Test component</h2>
    <h2>{{ this.$store.state.counter }}</h2>
    <hr />
    <input type="number" v-model="inputValue" placeholder="enter number" />
    <p>{{ inputValue }}</p>
    <button @click="increaseNumber">Increase</button>
  </div>
</template>

<script>
export default {
  name: 'TestContainer',
  data() {
    return {
      inputValue: 0,
    };
  },
  methods: {
    increaseNumber() {
      this.$store.commit('increase', this.inputValue);
    },
  },
};
</script>
