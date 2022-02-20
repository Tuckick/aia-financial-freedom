<template>
  <div>
    <PageTitle text="Career" />
    <h3>ตำแหน่งที่เปิดรับ</h3>
    <div class="position-career-container">
      <PositionCareer :position-data="data" />
    </div>
  </div>
</template>

<script>
import PageTitle from '../components/page-title.vue'
import PositionCareer from '@/components/pages/career/position-career-template.vue'
import CareerData from '@/content/positionCareerDate.json'

export default {
  name: 'Contact',
  components: {
    PageTitle,
    PositionCareer,
  },
  data() {
    return {
      data: CareerData,
    }
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';
h3 {
  margin-top: 40px;
  margin-bottom: 24px;
}
.position-career-container {
  max-width: 540px;

  @media (min-width: $desktop-start) and (max-width: $desktop) {
    max-width: 90%;
  }

  @media (min-width: $desktop-over) {
    max-width: $desktop;
  }
}
</style>
