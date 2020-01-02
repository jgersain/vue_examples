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

.toggle {
  position: relative;
  display: inline-block;
  -ms-flex-negative: 0;
  flex-shrink: 0;
  border-radius: 9999px;
  cursor: pointer;
  height: 1.5rem;
  width: 3rem;
}

.toggle:focus {
  outline: 0;
  -webkit-box-shadow: 0 0 0 4px rgba(52, 220, 178, 0.5);
  box-shadow: 0 0 0 4px rgba(184, 194, 192, 0.5);
}

.toggle:before {
  display: inline-block;
  border-radius: 9999px;
  height: 100%;
  width: 100%;
  background-color: #dae1e7;
  content: "";
  -webkit-box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
  -webkit-transition: background-color 0.2s ease;
  transition: background-color 0.2s ease;
}

.toggle[aria-checked="true"]:before {
  background-color: #0bc7b7;
}

.toggle:after {
  position: absolute;
  top: 0;
  left: 0;
  border-radius: 9999px;
  height: 1.5rem;
  width: 1.5rem;
  background-color: #fff;
  border-width: 1px;
  border-color: #dae1e7;
  -webkit-box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
  content: "";
  -webkit-transition: -webkit-transform 0.2s ease;
  transition: -webkit-transform 0.2s ease;
  transition: transform 0.2s ease;
  transition: transform 0.2s ease, -webkit-transform 0.2s ease;
  -webkit-transform: translateX(0);
  transform: translateX(0);
}

.toggle[aria-checked="true"]:after {
  -webkit-transform: translateX(1.5rem);
  transform: translateX(1.5rem);
}
</style>