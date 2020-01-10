<template lang="pug">
  dl.accordion.box(role="presentation")
    accordion-item(
      v-for="item in content"
      :multiple="multiple"
      :item="item"
      :groupId="groupId"
      :key="item.id"
    )
</template>

<script>
import AccordionItem from './AccordionItem';

export default {
  name: 'Accordion',
  props: {
    content: {
      type: Array,
      required: true,
    },
    multiple: {
      type: Boolean,
      default: false,
    }
  },
  components: {
    AccordionItem,
  },
  data() {
    return {
      groupId: '',
    };
  },
  mounted() {
    this.groupId = this.$el.id;
  },
};
</script>

<style>
.accordion {
  padding: 0;
}

.accordion div:not(:last-child) {
  border-bottom: 1px solid rgba(10, 10, 10, 0.1);
}

.accordion div:last-child .accordion-item-details {
  border-radius: 5px;
}

.accordion dd {
  margin-left: 0;
}

.accordion-item-trigger,
.accordion-item-details-inner {
  padding: 0.75rem 1.25rem;
}

.accordion-item-title {
  position: relative;
}

.accordion h4 {
  font-size: 1.25rem;
  margin-bottom: 0;
  padding-right: 1.25rem;
}

.accordion-item-trigger {
  width: 100%;
  text-align: left;
  background-color: transparent;
  border: none;
}

.accordion-item-details {
  overflow: hidden;
  background-color: whitesmoke;
}

.accordion-item-enter-active, .accordion-item-leave-active {
  will-change: height;
  transition: height 0.2s ease;
}
.accordion-item-enter, .accordion-item-leave-to {
  height: 0 !important;
}
</style>