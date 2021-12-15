<template>
  <section class="header-container">
    <nuxt-link
      class="logo-container"
      tag="img"
      :src="require('~/assets/logo/financial-freedom-logo.png')"
      to="/"
    />
    <Hamburger />
  </section>
</template>
<script>
import Hamburger from './menu/hamburger.vue'
export default {
  components: {
    Hamburger,
  },
}
</script>
<style lang="scss">
@import '~assets/scss/variables';

.header-container {
  display: flex;
  justify-content: space-around;
  background-color: $dark-gray;
  padding: 8px;
}
.logo-container {
  height: 100px;
}
</style>
