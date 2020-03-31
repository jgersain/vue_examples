<template>
  <div id="app" class="container mx-auto p-8 flex">
    <div class="max-w-md w-full mx-auto">
      <h1 class="text-4xl text-center mb-12 font-thin">Controlled components</h1>
      <div class="bg-white rounded-lg overflow-hidden shadow-2xl">
        <div class="p-8">
          <controlled-form 
            @submit="suscribeNewsletter"
            :model="form"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ControlledForm from './ControlledForm';

export default {
  name: 'App',
  data() {
    return {
      form: {
        email: '',
        newsletter: false,
      },
    };
  },
  methods: {
    suscribeNewsletter() {
      alert(JSON.stringify(this.form));
    },
  },
  components: {
    ControlledForm,
  },
};
</script>

 <style>
@import "https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css";
body {
  @apply bg-gray-200 text-gray-700 font-sans;
}
</style>