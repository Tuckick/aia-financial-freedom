<template>
  <slider class="carousel-container" animation="fade" style="height: 500px;">
    <slider-item
      v-for="(i, index) in carouselList"
      :key="index"
      class="slide-item"
    >
      <img
        :src="require(`../../../assets/image/carousel/${i.img}`)"
        alt="carousel img"
        class="img-slide-item"
      />
    </slider-item>
  </slider>
</template>
<script>
import { Slider, SliderItem } from 'vue-easy-slider'

export default {
  name: 'Carousel',

  components: {
    Slider,
    SliderItem,
  },
  data() {
    return {
      carouselList: [
        { img: 'poster-01.jpg' },
        { img: 'poster-02.jpg' },
        { img: 'poster-03.jpg' },
        { img: 'poster-04.jpg' },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.carousel-container {
  z-index: -1;
  margin: -20px -20px auto;
  .slide-item {
    width: 100%;
    height: 100%;
    .img-slide-item {
      width: inherit;
      height: inherit;
    }
  }
}
</style>
