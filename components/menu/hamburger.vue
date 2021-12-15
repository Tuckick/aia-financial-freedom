<template>
  <div class="hamburger-container">
    <font-awesome-icon
      :icon="['fa', 'bars']"
      size="2x"
      class="hamburger-icon"
      @click="showMenu"
    />
    <div
      v-if="isShow"
      class="tab-section"
      :class="{ 'tab-section-show': isShow }"
    >
      <font-awesome-icon
        :icon="['fa', 'times']"
        size="2x"
        class="close-icon"
        @click="closeMenu"
      />
      <ul class="menu-list-container">
        <nuxt-link to="/"
          ><li>
            <font-awesome-icon :icon="['fa', 'home']" @click="closeMenu" />
            <span>Home</span>
          </li></nuxt-link
        >
        <nuxt-link to="/"
          ><li>
            <font-awesome-icon
              :icon="['fa', 'hand-holding-heart']"
              @click="closeMenu"
            />
            <span>Products & Services</span>
          </li></nuxt-link
        >
        <nuxt-link to="/"
          ><li>
            <font-awesome-icon
              :icon="['fa', 'address-card']"
              @click="closeMenu"
            />
            <span>About us</span>
          </li></nuxt-link
        >
        <nuxt-link to="/"
          ><li>
            <font-awesome-icon :icon="['fa', 'th-large']" @click="closeMenu" />
            <span>Blog</span>
          </li></nuxt-link
        >
        <nuxt-link to="/"
          ><li>
            <font-awesome-icon
              :icon="['fa', 'address-book']"
              @click="closeMenu"
            />
            <span>Contact</span>
          </li></nuxt-link
        >
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Hamburger',
  data() {
    return {
      isShow: false,
    }
  },
  methods: {
    closeMenu() {
      this.isShow = false
    },
    showMenu() {
      this.isShow = true
    },
  },
}
</script>
<style lang="scss">
@import '~assets/scss/variables';

.hamburger-container {
  .hamburger-icon {
    padding-top: 36px;
    padding-right: 20px;
    color: $gold;
  }
  .tab-section {
    position: absolute;
    height: 100%;
    width: 0px;

    .close-icon {
      position: absolute;
      top: 16px;
      right: 16px;
      color: $dark-gray;
    }
    .menu-list-container {
      margin: 0;
      padding: 64px 0 0 16px;
      font-size: $regular;
      list-style-type: none;
      li {
        margin: 24px auto;
      }
      a {
        color: $dark-gray;
        text-decoration: none;
      }
    }
  }
  .tab-section-show {
    position: absolute;
    height: 100%;
    width: 60%;
    top: 0;
    right: 0;
    background-color: $white;
    box-shadow: -1px 0 1px #fbfbfb;
    transition: width 0.2s ease;
  }
}
</style>
