<template>
  <default-layout>
    <h1>This is the main content</h1>
  </default-layout>
</template>

<script>
// @ is an alias to /src
import DefaultLayout from '@/layouts/DefaultLayout.vue';

export default {
  name: 'HomePage',
  components: {
    DefaultLayout,
  },
};
</script>
