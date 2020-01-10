<template lang="pug">
  .accordion-item(
    :id="groupId + '-' + item.id"
    :class="{'is-active': item.active}"
  )
    dt.accordion-item-title
      button.accordion-item-trigger(
        @click="toggle"
      )
        h4.accordion-item-title-text
          | {{ item.title }}
        span.accordion-item-trigger-icon

    transition(
      name="accordion-item"
      @enter="startTransition"
      @after-enter="endTransition"
      @before-leave="startTransition"
      @after-leave="endTransition"
    )
      dd.accordion-item-details(
        v-if="item.active"
      )
        .accordion-item-details-inner(
          v-html="item.details"
        )
</template>

<script>
export default {
  name: "AccordionItem",
  props: {
    item: {
      type: Object,
      required: true,
    },
    multiple: {
      type: Boolean,
      default: false,
    },
    groupId: {
      type: String,
      required: true,
    }
  },
  methods: {
    toggle() {
      if (this.multiple) this.item.active = !this.item.active;
    },
    startTransition(el) {
      el.style.height = el.scrollHeight + 'px';
    },
    endTransition(el) {
      el.style.height = '';
    },
  },
};
</script>