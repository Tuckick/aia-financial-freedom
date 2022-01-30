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
      <div class="how-i-help">
        <strong>เราช่วยคุณได้อย่างไร?</strong>
        <Accordion class="accordion-container" :items="productsData" />
      </div>
      <div class="service-process-container">
        <strong>เราช่วยคุณได้อย่างไร?</strong>
        <p>
          การให้บริการจะมีการนัดพบ 1 – 2 ครั้ง แต่ละครั้งใช้เวลาประมาณ 1 – 2
          ชั่วโมง โดยแบ่งเป็น 6 ขั้นตอนดังนี้
        </p>
        <div
          v-for="(i, index) in serviceProcessItem"
          :key="index"
          class="service-process-section"
        >
          <div class="detail-service-process-section">
            <div class="number-service-process-section">
              <font-awesome-icon
                :icon="['fa', i.icon]"
                size="2x"
                class="icon-section"
              />
            </div>
            <div class="toppic-service-process-section">
              <span>{{ i.toppic }}</span
              ><br />
              <p>{{ i.desc }}</p>
            </div>
          </div>
          <div class="line-process-section" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PageTitle from '../components/page-title.vue'
import Devide from '../components/devide.vue'
import Accordion from '../components/accordion/Accordion.vue'
import ProductsData from '../content/productAndServicesData.json'

export default {
  name: 'ProductsAndServices',
  components: {
    PageTitle,
    Devide,
    Accordion,
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
      defaultIndex: null,
      activeIndex: this.defaultIndex,
      isActive: this.active || false,
      productsData: ProductsData,
      serviceProcessItem: [
        {
          icon: 'comments',
          toppic: 'แนะนำบริการ',
          desc: 'แนะนำตัวพูดคุยเพื่อสร้างความเข้าใจที่ตรงกัน',
        },
        {
          icon: 'pencil-alt',
          toppic: 'เก็บข้อมูล',
          desc: 'เก็บข้อมูลที่สำคัญและกำหนดเป้าหมาย',
        },
        {
          icon: 'book-reader',
          toppic: 'วิเคราะห์',
          desc: 'วิเคราะห์ข้อมูลเพื่อกำหนดแผนปฏิบัติตามเป้าหมาย',
        },
        {
          icon: 'chart-bar',
          toppic: 'นำเสนอแผน',
          desc: 'อธิบายผลวิเคราะห์และนำเสนอแผนปฏิบัติ',
        },
        {
          icon: 'handshake',
          toppic: 'ลงมือปฏิบัติ',
          desc: 'เริ่มต้นลงมือปฏิบัติตามแผนที่นำเสนอ',
        },
        {
          icon: 'sync-alt',
          toppic: 'อัพเดทสถานะปัจจุบัน',
          desc: 'ทบทวนและปรับแผนตามสถานการณ์อย่างน้อยปีละ 1 ครั้ง',
        },
      ],
    }
  },
  mounted() {
    this.toggle(0)
  },
  methods: {
    togleButton() {
      this.isActive = !this.isActive
    },
    toggle(newIndex) {
      this.activeIndex = newIndex
    },
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
    .how-i-help {
      margin: 24px 0;

      strong {
        color: $gray-desc;
        font-size: $extra;
        font-weight: 1000;
      }

      .accordion-container {
        width: 100%;
        margin: 24px 0;
      }
    }
    .service-process-container {
      position: relative;
      margin: 24px 0;

      strong {
        color: $gray-desc;
        font-size: $extra;
        font-weight: 1000;
      }
      .service-process-section {
        position: relative;

        .detail-service-process-section {
          display: flex;
          .number-service-process-section {
            width: 56px;
            height: 56px;
            color: white;
            background-color: $gold;
            border: 1px solid $gold;
            border-radius: 50%;

            .icon-section {
              margin: 10px;
              vertical-align: -webkit-baseline-middle;
            }
          }
          .toppic-service-process-section {
            color: $gray-desc;
            margin-left: 16px;
            margin-bottom: 32px;
            span {
              vertical-align: -webkit-baseline-middle;
            }
            p {
              margin: 4px 0;
              font-size: $smallest;
            }
          }
        }

        .line-process-section {
          position: absolute;
          top: 56px;
          left: 26px;
          height: 56px;
          width: 1px;
          background-color: $gold;
          border: 2px solid $gold;
        }
      }
      .service-process-section:last-child {
        .line-process-section {
          display: none;
        }
      }
    }
  }
}
</style>
