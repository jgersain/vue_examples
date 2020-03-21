<template>
  <div class="default-layout">
    <header-partial />
    <main class="main">
      <slot />
    </main>
    <footer-partial />
    <!-- MOdals -->
    <modal :show="modals.login" @close-modal="closeModal">
      <p>Modal content</p>
    </modal>
  </div>
</template>

<script>
import HeaderPartial from '@/partials/HeaderPartial.vue';
import FooterPartial from '@/partials/FooterPartial.vue';
import Modal from '@/components/Modal.vue';

import { mapGetters } from 'vuex';

export default {
  name: 'DefaultLayout',
  components: {
    HeaderPartial,
    FooterPartial,
    Modal,
  },
  computed: {
    ...mapGetters([
      'modals',
    ]),
  },
  methods: {
    closeModal() {
      this.$store.dispatch('TOGGLE_MODAL_STATE', {
        name: 'login',
        value: false,
      });
    },
  },
};
</script>

<style>
  .default-layout {
    border: 4px solid red;;
  }

  main {
    border: 3px solid green;
  }
</style>
