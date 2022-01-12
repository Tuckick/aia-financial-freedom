<template>
  <section>
    <Carousel />
    <div class="may-i-help-container">
      <h1>
        เราให้บริการสร้างสรรค์ และออกแบบแผนการเงินที่ตอบโจทย์
        "เป้าหมายและความต้องการ" ที่แตกต่างของผู้รับคำปรึกษาโดยนักวางแผนการเงิน
        CFP
      </h1>
    </div>
    <div class="why-us-section">
      <section class="topic">
        <font-awesome-icon
          :icon="['fa', 'map-marker-alt']"
          size="2x"
          class="topic-icon"
        />
        <span>Why Us</span>
      </section>
      <WhyUs />
    </div>
  </section>
</template>

<script>
import Carousel from '../components/pages/home/carousel.vue'
import WhyUs from '../components/pages/home/whyUs.vue'

export default {
  components: {
    Carousel,
    WhyUs,
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

.may-i-help-container {
  background-color: $dark-gray;
  text-align: center;
  padding: 30px 20px;
  margin: 0 -20px;

  h1 {
    color: $white;
    font-size: $regular;
    font-weight: 1000;
    line-height: 1.75;
  }
}
.why-us-section {
  align-content: center;
  .topic {
    display: flex;
    margin: 20px auto;
    .topic-icon {
      color: $gold;
      margin-right: 8px;
    }
    span {
      font-size: $extra;
      font-weight: 1000;
    }
  }
}
</style>
