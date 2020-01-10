<template lang="pug">
  fieldset.my-3
    .form-check.mb-3(v-for="disability in disabilities")
      input.form-check-input(
        type="checkbox"
        :id="'disability' + disability.id"
        :value="disability.id"
        :name="checkboxesName"
        :key="disability.id"
      )
      label.form-check-label(
        :for="'disability' + disability.id"
      ) {{ disability.description }}
</template>

<script>
export default {
  name: 'MultipleCheckboxes',
  props: {
    disabilities: {
      type: Array,
      required: true,
    },
  },
};
</script>