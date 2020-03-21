<template>
  <div class="default-layout">
    <header-partial />
    <main class="main">
      <slot />
    </main>
    <footer-partial />
  </div>
</template>

<script>
import HeaderPartial from '@/partials/HeaderPartial.vue';
import FooterPartial from '@/partials/FooterPartial.vue';

export default {
  name: 'DefaultLayout',
  components: {
    HeaderPartial,
    FooterPartial,
  },
};
</script>

<style>
  .default-layout {
    border: 4px solid red;;
  }

  main {
    border: 3px solid green;
  }
</style>
