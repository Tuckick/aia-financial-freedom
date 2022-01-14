<template>
  <div class="e-form-container">
    <form action="">
      <BaseInput
        id="fullName"
        :title="contents.fullName.title"
        :maxlength="contents.fullName.maxlength"
      />
      <BaseInput
        id="lineId"
        :title="contents.lineId.title"
        :maxlength="contents.lineId.maxlength"
      />
      <BaseInput
        id="contactNumber"
        :title="contents.contactNumber.title"
        :maxlength="contents.contactNumber.maxlength"
      />
      <BaseInput
        id="email"
        :title="contents.email.title"
        :maxlength="contents.email.maxlength"
      />
    </form>
  </div>
</template>
<script>
import BaseInput from '../components/base-input.vue'

export default {
  name: 'EForm',
  components: {
    BaseInput,
  },
  data() {
    return {
      contents: {
        fullName: {
          title: 'ชื่อ-นามสกุล',
          maxlengthซ: '85',
        },
        lineId: {
          title: 'Line ID',
          maxlengthซ: '30',
        },
        contactNumber: {
          title: 'เบอร์โทร',
          maxlengthซ: '10',
        },
        email: {
          title: 'E-Mail',
          maxlengthซ: '60',
        },
      },
    }
  },
  // validations: {
  //   fullName: {
  //     required,
  //     maxLength: maxLength(85),
  //   },
  //   lineId: {
  //     maxLength: maxLength(30),
  //   },
  //   contactNumber: {
  //     required,
  //     maxLength: maxLength(10),
  //     minLength: minLength(10),
  //     // phoneValidator,
  //   },
  //   email: {
  //     // emailValidator,
  //   },
  // },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.e-form-container {
  text-align: left;
}
</style>
