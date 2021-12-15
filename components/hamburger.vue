<template>
  <div class="hamburger-container">
    <font-awesome-icon :icon="['fa', 'bars']" size="2x" class="hamburger-icon" />
  </div>
</template>
<script>
export default {}
</script>
<style lang="scss">
@import '~assets/scss/variables';

.hamburger-container {
  .hamburger-icon {
    padding-top: 36px;
    padding-right: 20px;
    color: $gold;
  }
}
</style>
