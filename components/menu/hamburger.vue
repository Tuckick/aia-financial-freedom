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
      <div class="menu-list-container">
        <ul v-for="(i, index) in topic" :key="index" class="menu-list-items">
          <nuxt-link :to="i.pathTo"
            ><li @click="closeMenu">
              <font-awesome-icon :icon="['fa', i.iconName]" />
              <span>{{ i.pageName }}</span>
            </li></nuxt-link
          >
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Hamburger',
  props: {
    topic: {
      type: Object,
      required: true,
    },
  },
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
<style lang="scss" scoped>
@import '~assets/scss/variables';

.hamburger-container {
  text-align: left;
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
      margin-top: 64px;
      .menu-list-items {
        margin: 0;
        padding-left: 16px;
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
