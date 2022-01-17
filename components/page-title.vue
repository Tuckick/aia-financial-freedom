<template>
  <div class="page-title-section">
    <h1>{{ text }}</h1>
  </div>
</template>
<script>
export default {
  name: 'PageTitle',
  props: {
    text: {
      type: String,
      required: true,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.page-title-section {
  width: 100%;
  background-color: $smoke-gray;
  padding: 0;
  text-align: left;

  h1 {
    font-size: $extra;
    color: $gray-desc;
    padding: 20px;
    margin: 0;
  }
}
</style>
