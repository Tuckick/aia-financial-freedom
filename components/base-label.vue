<template>
  <div class="BaseLabel">
    <span>{{ title }}</span>
  </div>
</template>
<script>
export default {
  name: 'BaseLabel',
  props: {
    title: {
      type: String,
      required: true,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.BaseLabel {
  text-align: left;
  color: $dark-gray;
  span {
    font-size: $small;
  }
}
</style>
