<template>
  <div class="why-us-container">
    <UnborderCard :items="contents" />
  </div>
</template>
<script>
import UnborderCard from '../../unborder-card.vue'
import WhyUsData from '../../../content/whyUs.json'

export default {
  name: 'WhyUs',
  components: {
    UnborderCard,
  },
  data() {
    return {
      contents: WhyUsData,
    }
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.why-us-container {
  align-content: center;
  text-align: center;
  text-align: -webkit-center;
  .icon-section {
    width: fit-content;
    background-color: $gold;
    border-radius: 50%;
    padding: 20px;

    .icon {
      color: $white;
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
}
</style>
