<template lang="pug">
  .content
    h1.font-bold.mt-5 Acordeón
    hr.m-5

    section
      | Múltiple
      accordion#accordion(
        :content="content"
        multiple
      )

    h1.font-bold.mt-5 Casillas de verificación
    hr.m-5

    multiple-checkboxes(
      :disabilities="disabilities"
    )
</template>

<script>
import Accordion from './Accordion';
import MultipleCheckboxes from './MultipleCheckboxes';

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

const disabilities = [
  {
    id: 5,
    description: "Ceguera",
    parent_id: 3,
    verification_leyend: null
  },
  {
    id:6,
    description:"Debilidad visual",
    parent_id:3,
    verification_leyend:"¿Se corrige utilizando lentes?"
  },
  { 
    id: 7,
    description: "Sordera",
    parent_id: 1,
    verification_leyend: null
  },
  {
    id: 8,
    description: "Debilidad auditiva",
    parent_id: 1,
    verification_leyend: "¿Se corrige utilizando algún aparato?"
  },
  {
    id: 9,
    description: "Motora",
    parent_id: 2,
    verification_leyend: null
  }
];

export default {
  name: 'App',
  components: {
    Accordion,
    MultipleCheckboxes,
  },
  data() {
    return {
      content: exampleData,
      disabilities: disabilities,
    };
  },
};
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css";
</style>
