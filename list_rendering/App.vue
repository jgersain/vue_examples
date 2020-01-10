<template lang="pug">
  .content
    h1.font-bold Acordeón
    hr.m-5

    section
      | Múltiple
      accordion#accordion(
        :content="content"
        multiple
      )
</template>

<script>
import Accordion from './Accordion';

const exampleData = [
  {
    id: 1,
    active: false,
    title: 'The shit',
    details: 'come on, this is the firt shit...'
  },
  {
    id: 2,
    active: false,
    title: 'The shit 2',
    details: 'come on, this is shit twice...'
  },
  {
    id: 3,
    active: false,
    title: 'The shit 3',
    details: 'come on, this is shit three times...'
  }
];

export default {
  name: 'App',
  components: {
    Accordion,
  },
  data() {
    return {
      content: exampleData,
    };
  },
};
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css";
</style>
