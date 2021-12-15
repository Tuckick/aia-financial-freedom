<template>
  <section class="header-container">
    <nuxt-link
      class="logo-container"
      tag="img"
      :src="require('~/assets/logo/financial-freedom-logo.png')"
      to="/"
    />
    <Hamburger :topic="pages" />
  </section>
</template>
<script>
import Hamburger from './menu/hamburger.vue'
export default {
  components: {
    Hamburger,
  },
  data() {
    return {
      pages: [
        {
          pathTo: '/',
          iconName: 'home',
          pageName: 'Home',
        },
        {
          pathTo: '/',
          iconName: 'hand-holding-heart',
          pageName: 'Products & Services',
        },
        {
          pathTo: '/',
          iconName: 'address-card',
          pageName: 'About us',
        },
        {
          pathTo: '/',
          iconName: 'th-large',
          pageName: 'Blog',
        },
        {
          pathTo: '/',
          iconName: 'address-book',
          pageName: 'Contact',
        },
      ],
    }
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
