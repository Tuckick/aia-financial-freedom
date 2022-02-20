<template>
  <div class="tab-menu-section">
    <div v-for="(item, index) in topic" :key="index" class="menu-list">
      <nuxt-link :to="item.pathTo">
        <strong>{{ item.pageName }}</strong>
      </nuxt-link>
    </div>
  </div>
</template>
<script>
export default {
  name: 'TabMenu',
  props: {
    topic: {
      type: Array,
      required: true,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.tab-menu-section {
  height: 100px;
  .menu-list {
    align-self: center;
    margin: auto 20px;

    strong {
      color: $gold;
    }
    strong:hover {
      color: white;
      text-decoration: none;
    }
    strong:active {
      color: white;
      text-decoration: none;
    }
    a {
      color: $gold;
    }
    a:hover {
      color: white;
      text-decoration: none;
    }
    a:active {
      color: white;
      text-decoration: none;
    }
  }
}
</style>
