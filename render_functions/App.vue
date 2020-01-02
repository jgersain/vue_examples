<template lang="pug">
  .app.text-center.m-20
    button.bg-transparent.text-blue-700.font-semibold.py-2.px-4.border.border-blue-500.rounded(
      class='hover:bg-blue-500 hover:text-white hover:border-transparent'
      @click.prevent="toggleHandler"
    )
      | Mostrar mensaje
    transition(name="fade")
      modal-jsx(
        :show="show"
      ) 
        p 
          | Shut a fuck up...
</template>

<script>
import ModalJsx from './ModalJsx';

export default {
  name: 'App',
  data() {
    return {
      show: false,
    };
  },
  components: {
    ModalJsx,
  }, 
  methods: {
    toggleHandler() {
      this.show = !this.show;
    },
  },
};
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css";

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>