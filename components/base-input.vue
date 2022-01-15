<template>
  <div class="BaseInput">
    <BaseLabel :title="title" />
    <Input
      id="full-name"
      :type="type"
      :maxlength="maxlength"
      class="input-box"
    />
  </div>
</template>
<script>
import BaseLabel from '../components/base-label.vue'

export default {
  name: 'BaseInput',
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
      required: true,
    },
    type: {
      type: String,
      required: false,
      default: 'text',
    },
    maxlength: {
      type: Number,
      required: true,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.BaseInput {
  text-align: left;
  color: $dark-gray;
  font-size: $small;
  span {
    font-size: $small;
  }
  .input-box {
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
