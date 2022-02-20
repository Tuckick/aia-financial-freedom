<template>
  <section class="header-container">
    <nuxt-link
      class="logo-container"
      tag="img"
      :src="require('~/assets/logo/financial-freedom-logo.png')"
      to="/"
    />
    <Hamburger :topic="pages" class="show-hamburger" />
    <TabMenu :topic="pages" class="show-tab-menu" />
  </section>
</template>
<script>
import Hamburger from './menu/hamburger.vue'
import TabMenu from './menu/tabMenu.vue'

export default {
  components: {
    Hamburger,
    TabMenu,
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
          pathTo: '/ProductsAndServices',
          iconName: 'hand-holding-heart',
          pageName: 'Products & Services',
        },
        {
          pathTo: '/AboutUs',
          iconName: 'address-card',
          pageName: 'About us',
        },
        // {
        //   pathTo: '/Blog',
        //   iconName: 'th-large',
        //   pageName: 'Blog',
        // },
        {
          pathTo: '/Contact',
          iconName: 'address-book',
          pageName: 'Contact',
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.header-container {
  display: flex;
  justify-content: space-around;
  background-color: $dark-gray;
  padding: 8px;
  .show-tab-menu {
    display: none;
  }

  .logo-container {
    height: 100px;
  }

  @media (min-width: $desktop-start) {
    .show-hamburger {
      display: none;
    }
    .show-tab-menu {
      display: flex;
    }
  }
}
</style>
