<template>
  <span
    class="toggle mr-2 leading-tight"
    role="checkbox"
    tabindex="0"
    @click="toggle"
    :aria-checked="toggled.toString()"
  />
</template>

<script>
export default {
  name: 'ToggleInput',
  model: {
    prop: 'toggled',
    event: 'toggle',
  },
  props: {
    toggled: {
      type: Boolean,
      default: false,
    }
  },
  methods: {
    toggle() {
      this.$emit('toggle', !this.toggled);
    },
  },
};
</script>
