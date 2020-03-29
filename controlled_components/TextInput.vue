<template>
  <div>
    <label 
      :for="name"
      class="block mb-2 text-sm font-medium text-gray-600"
    > 
      {{ label }}
    </label>
    <input
      :id="name"
      :value="value"
      @input="$emit('input', $event.target.value)"
      class="block w-full p-3 rounded bg-gray-200 border border-transparent focus:outline-none" 
      :type="type"
      :placeholder="placeholder"
    >
  </div>
</template>

<script>
export default {
  name: 'TextInput',
  props: {
    name: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      default: 'text',
    },
    placeholder: {
      type: String,
      default: '',
    },
    value: {
      type: String,
      default: '',
    },
  },
}
</script>