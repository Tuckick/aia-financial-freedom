<template>
  <section class="footer-container">
    <div class="contact-address">
      <h4>ที่อยู่ ติดต่อ</h4>
      <p>
        138 ตึก JCB ชั้นที่ 21 แขวงสี่พระยา เขตบางรัก 10500 กรุงเทพมหานคร 10500
      </p>
      <a href="www.google.com">www.google.com</a><br />
      <a href="tel:055248607">Tel.05-5248607</a>
    </div>
    <div class="follow-social">
      <h4>Follow</h4>
      <Devide />
      <font-awesome-icon :icon="['fa', 'times']" size="2x" />
      <font-awesome-icon :icon="['fa', 'times']" size="2x" />
      <font-awesome-icon :icon="['fa', 'times']" size="2x" />
    </div>
    <div class="our-products">
      <h4>แผนการเงินที่เราให้บริการ</h4>
      <ul>
        <li><a href=""> การวางแผนเกษียณอายุ </a></li>
        <li><a href=""> การวางแผนภาษี </a></li>
        <li><a href=""> การวางแผนประกันภัย </a></li>
        <li><a href=""> การวางแผนการศึกษาบุตร </a></li>
        <li><a href=""> การวางแผนการลงทุน </a></li>
        <li><a href=""> การวางแผนการส่งต่อมรดก </a></li>
      </ul>
    </div>
  </section>
</template>

<script>
import Devide from '../components/devide.vue'

export default {
  name: 'Footer',
  components: {
    Devide,
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

.footer-container {
  width: 100%;
  background-color: $dark-gray;

}
.logo-container {
  height: 100px;
}
ul {
  list-style: none;
}
</style>
