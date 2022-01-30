<template>
  <div class="about-us-container">
    <PageTitle text="About us" />
    <div class="about-us-container-body">
      <div class="who-are-we">
        <strong>เราคือใคร ?</strong>
        <p>
          Financial Freedom เป็นหนึ่งในผู้นำในธุรกิจการวางแผนการเงินส่วนบุคคล
          ซึ่งการให้บริการของเราครอบคลุมถึงการออกแบบแผนการเงินเฉพาะบุคคล
          อันประกอบไปด้วยแผนเกษียณอายุ แผนการลงทุน แผนประกันชีวิต/ประกันสุขภาพ
          แผนการศึกษาบุตร และแผนมรดก ปัจจุบันเราให้บริการมากกว่า 340 ครอบครัว
          ทั้งนี้เรายังมีส่วนร่วมสำคัญในการพลักดันบริการเพื่อสังคมต่างๆ มากมาย
          โดยผู้ให้คำแนะนำของเรามีใบอนุญาตตามกฎหมายในการเสนอผลิตภัณฑ์ทางการเงิน
          เช่น
        </p>
        <ul>
          <li>
            <b>ใบอนุญาตตัวแทนประกันชีวิต และนายหน้าวินาศภัย</b>
            กรณีแนะนำประกันชีวิตหรือประกันสุขภาพ
            ซึ่งควบคุมโดยสำนักงานคณะกรรมการกำกับและส่งเสริมการประกอบธุรกิจประกันภัย
            (คปภ.)
          </li>
          <li>
            <b>ใบอนุญาตเป็นผู้แนะนำหรือผู้วางแผนการลงทุน (IP License)</b>
            ในกรณีแนะนำกองทุนรวมประเภทต่างๆ
            ซึ่งควบคุมโดยสำนักงานคณะกรรมการกำกับหลักทรัพย์และตลาดหลักทรัพย์
            (ก.ล.ต.)
          </li>
          <li>
            <b>คุณวุฒิวิชาชีพนักวางแผนการเงิน (CFP)</b>
            กรณีแนะนำแนวทางการบริหารเงินส่วนบุคคล
            ซึ่งได้รับเมื่อผ่านการทดสอบของสมาคมนักวางแผนการเงินไทยเป็นการรับรองความสามารถของที่ปรึกษาการเงินในการให้บริการวางแผน
          </li>
        </ul>
      </div>
      <Devide />
      <div class="responsibility-container">
        <div style="height: 48px" />
        <strong>ความรับผิดชอบต่อสังคม</strong>
        <div style="height: 24px" />
        <Card :items="responsibilityData" background-color="dark-blue" />
        <Devide />
      </div>
      <div class="values-container">
        <div style="height: 48px" />
        <strong>ค่านิยม</strong>
        <div style="height: 24px" />
        <Card :items="valuesData" background-color="dark-gray" />
        <Devide />
      </div>
    </div>
  </div>
</template>
<script>
import PageTitle from '../components/page-title.vue'
import Devide from '../components/devide.vue'
import Card from '../components/unborder-card.vue'
import ResponsibilityData from '../content/responsibility.json'
import ValuesData from '../content/values.json'

export default {
  name: 'AboutUs',
  components: {
    PageTitle,
    Devide,
    Card,
  },
  data() {
    return {
      responsibilityData: ResponsibilityData,
      valuesData: ValuesData,
    }
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.about-us-container {
  padding: 0;
  .about-us-container-body {
    padding: 40px 20px;

    .who-are-we {
      text-align: left;
    }
  }
}

strong {
  color: $gray-desc;
  font-size: $extra;
  font-weight: 1000;
  padding: 0;
}
</style>
