<template>
  <button>{{text}}</button>
</template>
<script>
export default {
  name: 'Button',
  props: {
    text: {
      type: String,
      default: 'Okay',
      required: false,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

button {
  background-color: $gold;
  color: white;
  padding: 8px;
  border: none;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: $smallest;
  margin: 16px 0px;
  cursor: pointer;
}
</style>
