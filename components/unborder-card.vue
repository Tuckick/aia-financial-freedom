<template>
  <div class="unborder-card-container">
    <div v-for="(i, index) in items" :key="index">
      <section class="icon-section" :class="backgroundColor">
        <font-awesome-icon :icon="['fa', i.icon]" size="3x" class="icon" />
      </section>
      <section class="topic-section">
        <span>{{ i.title }}</span>
      </section>
      <section class="desc-section">
        <span>
          {{ i.desc }}
        </span>
      </section>
    </div>
  </div>
</template>
<script>
export default {
  name: 'UnborderCard',
  props: {
    items: {
      type: Array,
      required: true,
    },
    backgroundColor: {
      type: String,
      default: 'gold',
      require: false,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.unborder-card-container {
  align-content: center;
  text-align: center;
  text-align: -webkit-center;
  .icon-section {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    padding-top: 14px;

    .icon {
      color: $white;
      padding-top: 6px;
    }
  }
  .topic-section {
    color: black;
    font-size: $large;
    font-weight: bold;
    margin-top: 16px;
  }
  .desc-section {
    color: $gray-desc;
    font-size: $meduim;
    line-height: 1.4;
    margin-top: 8px;
    margin-bottom: 40px;
  }
  .gold {
    background-color: $gold;
  }

  .gray {
    background-color: $gray;
  }

  .dark-gray {
    background-color: $dark-gray;
  }

  .dark-blue {
    background-color: $dark-blue;
  }

  .light-gray {
    background-color: $light-gray;
  }
}
</style>
