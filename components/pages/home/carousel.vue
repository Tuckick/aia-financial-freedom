<template>
  <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="inherit"
      style="text-shadow: 1px 1px 2px #333"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <b-carousel-slide
        img-src="@/assets/image/carousel/poster-01.jpg"
      ></b-carousel-slide>
      <b-carousel-slide
        img-src="@/assets/image/carousel/poster-02.jpg"
      ></b-carousel-slide>
      <b-carousel-slide
        img-src="@/assets/image/carousel/poster-03.jpg"
      ></b-carousel-slide>
      <b-carousel-slide
        img-src="@/assets/image/carousel/poster-04.jpg"
      ></b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
    }
  },
  methods: {
    onSlideStart(slide) {
      this.sliding = true
    },
    onSlideEnd(slide) {
      this.sliding = false
    },
  },
}
</script>
