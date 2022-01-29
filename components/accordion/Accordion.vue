<template>
  <div class="accordion-pack-layout">
    <AccordionButton
      v-for="(item, index) in filterActiveItem"
      :id="item.id"
      :key="index"
      :active="activeIndex === index"
      :title="item.title"
      :ga-tag-id="item.id"
    >
      <template #content>
        <!-- eslint-disable vue/no-v-html -->
        <AccordionContentTextBody v-html="item.content" />
        <!--eslint-enable-->
      </template>
    </AccordionButton>
  </div>
</template>

<script>
import AccordionButton from '@/components/accordion/AccordionButton.vue'
import AccordionContentTextBody from '@/components/accordion/AccordionContentTextBody.vue'

export default {
  name: 'Accordion',
  components: {
    AccordionButton,
    AccordionContentTextBody,
  },
  props: {
    items: {
      type: Array,
      required: true,
      default: () => [],
    },
    defaultIndex: {
      type: Number,
      required: false,
      default: null,
    },
    limit: {
      type: Number,
      required: false,
      default: 0,
    },
  },
  data() {
    return {
      activeIndex: this.defaultIndex,
    }
  },
  computed: {
    filterActiveItem() {
      let limitIdx = this.items.length
      if (this.limit !== 0) {
        limitIdx = this.limit
      }
      return this.items.filter(this.isAvailable).slice(0, limitIdx)
    },
  },
  mounted() {
    this.toggle(0)
  },
  methods: {
    isAvailable(item) {
      return item.visible
    },
    toggle(newIndex) {
      this.activeIndex = newIndex
    },
  },
}
</script>

<style lang="scss" scoped>
.accordion-pack-layout {
  display: grid;
  grid-template-columns: 1fr;
  grid-auto-rows: max-content;
}
</style>
