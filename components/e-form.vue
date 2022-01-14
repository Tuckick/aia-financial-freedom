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
      <BaseInput
        id="email"
        :title="contents.email.title"
        :maxlength="contents.email.maxlength"
      />
      <BasedDropdown
        id="productList"
        :options="listProduct"
        :validate-click-out-side="true"
        :title="contents.product.title"
        :placeholder="contents.product.placeholder"
      />
    </form>
  </div>
</template>
<script>
import BaseInput from '../components/base-input.vue'
import BasedDropdown from '../components/base-dropdown.vue'


export default {
  name: 'EForm',
  components: {
    BaseInput,
    BasedDropdown
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
        product: {
          title: 'แผนที่ต้องการ',
          placeholder: 'เลือกแผนที่ต้องการ',
        },
      },
      listProduct: [
        { value: 'วางแผนประกันภัย', title: 'วางแผนประกันภัย' },
        { value: 'วางแผนเกษียณอายุ', title: 'วางแผนเกษียณอายุ' },
        { value: 'วางแผนการศึกษาบุตร', title: 'วางแผนการศึกษาบุตร' },
        { value: 'วางแผนการลงทุน', title: 'วางแผนการลงทุน' },
        { value: 'วางแผนภาษี', title: 'วางแผนภาษี' },
        { value: 'วางแผนมรดก', title: 'วางแผนมรดก' },
        { value: 'วางแผนอื่นๆ', title: 'วางแผนอื่นๆ' },
      ],
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
  // product: {
  //     required,
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
