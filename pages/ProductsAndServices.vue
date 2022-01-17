<template>
  <div class="products-and-services-container">
    <PageTitle text="Products & Services" />
    <div class="products-and-services-container-body">
      <div class="explanded-list">
        <ul class="for-who">
          บริการนี้เหมาะกับใคร ?
          <li>คนที่ต้องการเริ่มต้นวางแผนชีวิตอย่างถูกต้อง</li>
          <li>ไม่จำกัดอายุ ระดับการศึกษา</li>
          <li>ไม่จำกัดเงินเรื่องรายได้ หรือเงินเริ่มต้นลงทุน</li>
          <li>ยินดีเปิดเผยข้อมูลการเงินส่วนตัวได้</li>
        </ul>
        <ul class="how-much">
          คิดค่าบริการอย่างไร ?
          <li>
            ค่าที่ปรึกษาครั้งแรก: <strong style="color: red">ไม่มี</strong>
          </li>
          <li>
            ค่าใช้จ่ายในการวางแผน:
            <strong style="color: rgb(50, 50, 50)"
              >ขึ้นอยู่กับความยากง่ายของแผนการเงิน</strong
            >
            (ค่าบริการจะแจ้งก่อนเริ่มวางแผนจริง)
          </li>
          <li>
            ท่านไม่มีข้อผูกมัดในการรับบริการจากเรา
            การตัดสินใจของท่านขึ้นอยู่กับความพึงพอใจในคำแนะนำเบื้องต้นของเรา
          </li>
        </ul>
        <Devide />
      </div>
    </div>
  </div>
</template>

<script>
import PageTitle from '../components/page-title.vue'
import Devide from '../components/devide.vue'

export default {
  name: 'ProductsAndServices',
  components: {
    PageTitle,
    Devide,
  },
  data() {
    return {
      explandedItems: {
        forWho: {
          title: 'บริการนี้เหมาะกับใคร?',
          list: [
            'คนที่ต้องการเริ่มต้นวางแผนชีวิตอย่างถูกต้อง',
            'ไม่จำกัดอายุ ระดับการศึกษา',
            'ไม่จำกัดเงินเรื่องรายได้ หรือเงินเริ่มต้นลงทุน',
            'ยินดีเปิดเผยข้อมูลการเงินส่วนตัวได้',
          ],
        },
        howMuch: {
          title: 'คิดค่าบริการอย่างไร?',
          list: [
            'ค่าที่ปรึกษาครั้งแรก: ไม่มี',
            'ขึ้นอยู่กับความยากง่ายของแผนการเงิน (ค่าบริการจะแจ้งก่อนเริ่มวางแผนจริง)',
            'ท่านไม่มีข้อผูกมัดในการรับบริการจากเรา การตัดสินใจของท่านขึ้นอยู่กับความพึงพอใจในคำแนะนำเบื้องต้นของเรา',
          ],
        },
      },
    }
  },
}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

.products-and-services-container {
  padding: 0;

  .products-and-services-container-body {
    padding: 40px 20px;
    text-align: left;

    .explanded-list {
      ul {
        color: $gray-desc;
        font-size: $extra;
        font-weight: 1000;
        padding: 0;

        li {
          font-size: $meduim;
          line-height: 2;
          margin-left: 32px;
        }
        li:first-child {
          margin-top: 16px;
        }
      }
    }
  }
}
</style>
