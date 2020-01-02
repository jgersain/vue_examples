<template>
  <div id="app" class="container mx-auto p-8 flex">
    <div class="max-w-md w-full mx-auto">
      <h1 class="text-4xl text-center mb-12 font-thin">Controlled components</h1>
      <div class="bg-white rounded-lg overflow-hidden shadow-2xl">
        <div class="p-8">
          <form @submit.prevent="suscribeNewsletter">
            <div class="mb-5">
              <label for="email" class="block mb-2 text-sm font-medium text-gray-600">
                Email
              </label>
              <input
                id="email"
                class="block w-full p-3 rounded bg-gray-200 border border-transparent focus:outline-none"
                type="text"
                v-model="form.email"
                name="email"
                placeholder="john@connor.org">
            </div>
            <div class="mb-4">
              <label class="block text-grey font-bold flex items-center">
                <toggle-input v-model="form.newsletter" />
                <span class="text-sm">
                  ¡Enviarme promociones!
                </span>
              </label>
            </div>
            <div class="mb-4">
              <button class="w-full bg-teal-400 text-white p-3 mt-4 rounded shadow hover:bg-teal-500">Registrar</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ToggleInput from './ToggleInput.vue';

export default {
  name: 'App',
  data() {
    return {
      form: {
        email: '',
        newsletter: false,
      }
    };
  },
  methods: {
    suscribeNewsletter() {
      alert(JSON.stringify(this.form));
    },
  },
  components: {
    ToggleInput,
  },
};
</script>

 <style>
@import "https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css";
body {
  @apply bg-gray-200 text-gray-700 font-sans;
}
</style>