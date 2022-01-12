<template>
  <section>
    <Carousel />
    <div class="may-i-help-container">
      <span>
        เราให้บริการสร้างสรรค์
        และออกแบบแผนการเงินที่ตอบโจทย์ "เป้าหมายและความต้องการ"
        ที่แตกต่างของผู้รับคำปรึกษาโดยนักวางแผนการเงิน CFP
      </span>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import '~assets/scss/variables';

.may-i-help-container {
  background-color: $dark-gray;
  text-align: center;
  padding: 30px 20px;
  margin: 0 -20px;
  
  span {
    color: $white;
    font-size: 18px;
    line-height: 1.5;
  }
}
</style>
