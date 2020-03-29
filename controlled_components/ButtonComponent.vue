<template>
  <button
    class="bg-teal-400 w-full p-3 text-white rounded shadow hover:bg-teal-500"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'ButtonComponent',
}
</script>