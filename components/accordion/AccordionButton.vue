<template>
  <div class="accordion-container" :class="{ isActive }">
    <div class="accordion-title-wrapper" :class="gaTagId" @click="toggle">
      <!-- eslint-disable vue/no-v-html -->
      <h3 class="accordion-title" :class="gaTagId" v-html="title" />
      <!--eslint-enable-->
      <div class="icon-wrapper" :class="gaTagId">
        <img
          draggable="false"
          class="arrow"
          :class="[{ isActive }, gaTagId]"
          src="~@/assets/icons/accordion/icon-arrow-down.svg"
          alt="arrow-down-icon"
        />
      </div>
    </div>

    <div
      ref="item"
      class="accordion-content-wrapper"
      style="visibility: hidden"
    >
      <div class="accordion-content-layout">
        <slot name="content" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AccordionButton',
  props: {
    title: {
      type: String,
      required: false,
      default: null,
    },
    content: {
      type: String,
      required: false,
      default: null,
    },
    active: {
      type: Boolean,
      required: false,
      default: false,
    },
    gaTagId: {
      type: String,
      required: false,
      default: null,
    },
  },
  data() {
    return {
      isActive: this.active || false,
    }
  },
  watch: {
    active(active) {
      this.isActive = active
    },
    isActive(isActive) {
      if (isActive) {
        this.open()
      } else {
        this.close()
      }
    },
  },
  methods: {
    toggle() {
      this.isActive = !this.isActive
    },
    open() {
      const item = this.$refs.item
      item.style.maxHeight = `${item.scrollHeight + 300}px`
      item.style.visibility = 'visible'
    },
    close() {
      const item = this.$refs.item
      item.style.maxHeight = 0
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

.accordion-container {
  width: 100%;
  background: #fff;
  border-bottom: 1px solid hsla(0, 36%, 38%, 0.08);

  &:focus {
    outline: none;
  }
  .divider {
    margin-bottom: 0px;
    &::before {
      height: 0px;
    }
  }
}
.accordion-title-wrapper {
  display: grid;
  grid-template-columns: 1fr 36px;
  padding: 21px 0 20px 0;
  cursor: pointer;
}
.accordion-title {
  font-size: 16px;
  font-weight: bold;
  line-height: 26px;
  color: $dark-blue;
  text-align: left;
  margin-bottom: 0px;
  display: flex;
  align-items: center;
  padding-left: 8px;
  padding-right: 8px;
}
.icon-wrapper {
  display: flex;
  justify-content: center;
}
.accordion-content-wrapper {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.6s ease-in-out;

  .line {
    border-bottom: 1px solid $gold;
    width: 0px;
    &.isActive {
      width: 100%;
      transition-property: width;
      transition-duration: 0.5s;
      transition-delay: 0.1s;
    }
  }
}
.accordion-content-layout {
  text-align: left;
  padding: 15px 8px 0px;
}
.arrow {
  transition: transform 0.2s ease-out;
  &.isActive {
    transform: rotate(180deg);
  }
}
</style>
