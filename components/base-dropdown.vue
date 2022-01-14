<template>
  <div class="BasedDropdown">
    <BaseLabel :title="title" />
    <select
      id="id"
      name="id"
      class="field-selected"
      :class="{ placeholder: selected == null }"
      @change="handleChange"
    >
      <option v-if="placeholder" disabled :selected="selected == null">
        {{ placeholder }}
      </option>
      <option
        v-for="item in options"
        :key="item.value"
        :value="item.value"
        :selected="selected == item.value"
      >
        {{ item.title }}
      </option>
    </select>
  </div>
</template>

<script>
import BaseLabel from '../components/base-label.vue'

export default {
  name: 'BasedDropdown',
  components: {
    BaseLabel,
  },
  props: {
    id: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: false,
      default: '',
    },
    value: {
      type: [Array, String, Number],
      required: false,
      default: null,
    },
    options: {
      type: Array,
      required: true,
    },
    placeholder: {
      type: String,
      required: true,
      default: null,
    },
  },
  data() {
    return {
      selected: this.value || null,
    }
  },
  methods: {
    handleChange(e) {
      const { value } = e.target
      this.selected = value
      this.$emit('input', value)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

.BasedDropdown {
  display: block;
  text-align: left;
  color: $dark-gray;
  font-size: $small;
  span {
    font-size: $small;
  }

  .field-selected {
    width: 100%;
    height: 40px;
    font-size: $small;
    color: $light-gray;
    float: none;
    display: inline-block;
    box-sizing: border-box;
    border-radius: 4px;
    border: 1px solid $light-gray;
    margin: 4px auto 16px;
    padding: 8px;
  }
}
</style>
