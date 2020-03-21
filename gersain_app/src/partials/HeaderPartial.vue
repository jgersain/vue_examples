<template>
  <header>
    <h1>Header component</h1>
    <button @click.prevent="getLogin">Show Modal</button>
  </header>
</template>

<script>
export default {
  name: 'HeaderPartial',
  methods: {
    getLogin() {
      this.$store.dispatch('TOGGLE_MODAL_STATE', {
        name: 'login',
        value: true,
      });
    },
  },
};
</script>

<style>
  header {
    border: 3px solid blueviolet;
  }
</style>
