<template>
  <section>
    <div
      v-for="(i, index) in positionData"
      :key="index"
      class="position-career-container"
    >
      <span><b>ตำแหน่ง :</b> {{ i.position }}</span>
      <div class="detail-container">
        <p><b>รายละเอียดงาน</b></p>
        <ul v-for="(detail, indexDetail) in i.detail" :key="indexDetail">
          <li>{{ detail }}</li>
        </ul>
        <p><b>คุณสมบัติ</b></p>
        <ul v-for="(feature, indexFeature) in i.feature" :key="indexFeature">
          <li>{{ feature }}</li>
        </ul>
      </div>
    </div>
    <div class="line" />
    <CareerContact />
  </section>
</template>
<script>
import CareerContact from '@/components/pages/career/career-contact.vue'

export default {
  name: 'PositionCareer',
  components: {
    CareerContact,
  },
  props: {
    positionData: {
      type: Array,
      required: true,
    },
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.position-career-container {
  text-align: left;
  padding: 0 20px;
  color: $light-gray;

  b {
    color: black;
  }
}
.line {
  height: 1px;
  width: 80%;
  background-color: $gold;
  margin-bottom: 40px;
}
</style>
