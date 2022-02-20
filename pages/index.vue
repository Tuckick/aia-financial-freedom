<template>
  <div>
    <Carousel id="home-carousel" />
    <div class="may-i-help-container">
      <h1>
        เราให้บริการสร้างสรรค์ และออกแบบแผนการเงินที่ตอบโจทย์
        "เป้าหมายและความต้องการ" ที่แตกต่างของผู้รับคำปรึกษาโดยนักวางแผนการเงิน
        CFP
      </h1>
    </div>
    <section class="home-container">
      <div
        v-for="(i, index) in topicList"
        :key="index"
        class="topic-at-home-page"
      >
        <section class="topic">
          <font-awesome-icon
            :icon="['fa', 'map-marker-alt']"
            size="2x"
            class="topic-icon"
          />
          <span>{{ i.name }}</span>
        </section>
        <component :is="i.component"></component>
      </div>
    </section>
  </div>
</template>

<script>
import Carousel from '../components/pages/home/carousel.vue'
import WhyUs from '../components/pages/home/whyUs.vue'
import ProductsAndServices from '../components/pages/home/productNservice.vue'

export default {
  components: {
    Carousel,
    WhyUs,
    ProductsAndServices,
  },
  data() {
    return {
      topicList: [
        { name: 'Why Us', component: 'WhyUs' },
        { name: 'Products and Services', component: 'ProductsAndServices' },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

#home-carousel {
  width: 100vw;
}
.may-i-help-container {
  background-color: $dark-gray;
  text-align: center;
  padding: 30px 20px;

  h1 {
    color: $white;
    font-size: $regular;
    font-weight: 1000;
    line-height: 1.75;
  }
}
.home-container {
  max-width: 540px;
  padding: 20px 20px 0;

  .topic-at-home-page {
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

  @media (min-width: $desktop-start) and (max-width: $desktop) {
    max-width: 90%;

    h1 {
      font-size: $extra;
    }
  }

  @media (min-width: $desktop-over) {
    max-width: $desktop;
    h1 {
      font-size: $extra;
    }
  }
}
</style>
