<template>
  <form
    @submit.prevent="$emit('submit')"
  >
    <div class="mb-5">
      <text-input 
        v-model="model.email"
        name="email"
        label="Correo electrónico"
        type="email"
        placeholder="john@connor.com"
      />
    </div>
    <div class="mb-4">
      <label class="block text-grey font-bold flex items-center">
        <toggle-input v-model="model.newsletter" />
        <span class="text-sm">
          ¡Enviarme promociones!
        </span>
      </label>
    </div>
    <div class="mb-4">
      <button-component>
        Registrar
      </button-component>
    </div>
  </form>
</template>

<script>
import TextInput from './TextInput';
import ToggleInput from './ToggleInput.vue';
import ButtonComponent from './ButtonComponent';

export default {
  name: 'ControlledForm',
  components: {
    TextInput,
    ToggleInput,
    ButtonComponent,
  },
  props: {
    model: {
      type: Object,
      required: true
    }
  },
}
</script>