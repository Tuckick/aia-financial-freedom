<template>
  <div class="career-contact-container">
    <p>
      ผู้ที่สนใจสามารถส่งใบสมัครให้เราได้ที่ :
      <br />
      <a href="https://www.m.me/Financial-Freedom-106150858289271/"
        >facebook inbox</a
      >
    </p>
  </div>
</template>
<script>
export default {
  name: 'CareerContact',
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.career-contact-container {
  color: $gray-desc;
  text-align: left;
  padding: 0 20px 40px;

  a {
    text-decoration: none;
    line-height: 1.8;
    color: $light-gray;
  }
}
</style>
