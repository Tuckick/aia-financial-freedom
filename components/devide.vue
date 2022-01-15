<template>
  <div :class="styleType" />
</template>
<script>
export default {
  name: 'Devide',
  props: {
    styleType: {
      type: String,
      default: 'dark-gray-divide',
      require: false,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.dark-gray-divide {
  width: 40px;
  border: 0.5px solid $dark-gray;
}
.white-divide {
  width: 40px;
  border: 0.5px solid white;
}
.gold-divide {
  width: 40px;
  border: 0.5px solid $gold;
}
.light-gray-devide {
  width: 40px;
  border: 0.5px solid $light-gray;
}
</style>
