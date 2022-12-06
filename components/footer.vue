<template>
  <section class="footer-container">
    <div class="contact-address">
      <h4 class="toppic-contact-address">ที่อยู่ ติดต่อ</h4>
      <p class="contact-address-desc">
        เลขที่ 138 ชั้น 23 ซอยนเรศ แขวงสี่พระยา เขตบางรัก กรุงเทพฯ ปณ.10500
      </p>
    </div>
    <div class="follow-social">
      <h4 class="toppic-follow-social">Follow</h4>
      <Devide style-type="gold-divide" />
      <a href="https://www.facebook.com/financialF245/" target="_blank">
        <font-awesome-icon
          class="icon-social"
          :icon="['fab', 'facebook-square']"
          size="2x"
        />
      </a>

      <a href="https://lin.ee/tFwfapW" target="_blank">
        <font-awesome-icon
          class="icon-social"
          :icon="['fab', 'line']"
          size="2x"
        />
      </a>
    </div>
    <div class="our-products">
      <h4 class="toppic-our-products">แผนการเงินที่เราให้บริการ</h4>
      <Devide style-type="gold-divide" />
      <ul>
        <li>การวางแผนเกษียณอายุ</li>
        <li>การวางแผนภาษี</li>
        <li>การวางแผนประกันภัย</li>
        <li>การวางแผนการศึกษาบุตร</li>
        <li>การวางแผนการลงทุน</li>
        <li>การวางแผนการส่งต่อมรดก</li>
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
  background-color: $dark-gray;
  text-align: left;
  font-size: $meduim;
  color: white;
  padding: 20px;

  .contact-address {
    .toppic-contact-address {
      font-size: $super-extra;
      color: $gold;
      margin: 32px auto 0;
      font-weight: 900;
    }
    .contact-address-desc {
      margin: 8px auto 16px;
      line-height: 1.8;
    }
  }

  .follow-social {
    .toppic-follow-social {
      font-size: $regular;
      margin: 32px auto 8px;
      font-weight: 1000;
    }
    .icon-social {
      margin-top: 16px;
      margin-right: 8px;
    }
  }

  .our-products {
    .toppic-our-products {
      font-size: $regular;
      margin: 32px auto 8px;
      font-weight: 1000;
    }
    ul {
      li {
        margin-bottom: 4px;
      }
    }
  }
  a {
    color: white;
    font-size: $meduim;
    text-decoration: none;
    line-height: 1.8;
  }
}
.logo-container {
  height: 100px;
}
ul {
  list-style: none;
  margin: 16px 0 0;
  padding: 0;
}
</style>
