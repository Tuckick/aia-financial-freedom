<template>
  <div class="why-us-container">
    <div v-for="(i, index) in contents" :key="index">
      <section class="icon-section">
        <font-awesome-icon :icon="['fa', i.icon]" size="3x" class="icon" />
      </section>
      <section class="topic-section">
        <span>{{ i.title }}</span>
      </section>
      <section class="desc-section">
        <span>
          {{ i.desc }}
        </span>
      </section>
    </div>
  </div>
</template>
<script>
export default {
  name: 'WhyUs',
  data() {
    return {
      contents: [
        {
          icon: 'user-alt',
          title: 'Expertise',
          desc: 'ด้วยทีมงานมากประสบการณ์ คุณจึงมั่นใจได้ว่าแผนการเงินของคุณได้รับการดูแลอย่างมืออาชีพและเป็นระบบ',
        },
        {
          icon: 'wrench',
          title: 'Personalize',
          desc: 'เพราะเป้าหมายของแต่ละคนไม่เหมือนกัน แผนการเงินจึงถูกออกแบบให้มีความเหมาะสมในแต่ละบุคคล',
        },
        {
          icon: 'shield-alt',
          title: 'Reliable',
          desc: 'ความไว้วางใจคือสิ่งที่เราให้ความสำคัญ เรายืนหยัดในการแนะนำสิ่งที่ดีสุดเพื่อประโยชน์ของคุณ',
        },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.why-us-container {
  align-content: center;
  text-align: center;
  text-align: -webkit-center;
  .icon-section {
    width: fit-content;
    background-color: $gold;
    border-radius: 50%;
    padding: 20px;

    .icon {
      color: $white;
    }
  }
  .topic-section {
    color: black;
    font-size: $large;
    font-weight: bold;
    margin-top: 16px;
  }
  .desc-section {
    color: $gray-desc;
    font-size: $meduim;
    line-height: 1.4;
    margin-top: 8px;
    margin-bottom: 40px;
  }
}
</style>
