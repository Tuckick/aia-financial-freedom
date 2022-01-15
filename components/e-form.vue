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
      <BaseDatePicker id="dealDate" :title="contents.dealDate.title" />
      <BasedDropdown
        id="timeList"
        :options="listTime"
        :validate-click-out-side="true"
        :title="contents.dealTime.title"
        :placeholder="contents.dealTime.placeholder"
      />
      <SubmitButton text="ส่งข้อมูล" />
    </form>
  </div>
</template>
<script>
import BaseInput from '../components/base-input.vue'
import BasedDropdown from '../components/base-dropdown.vue'
import BaseDatePicker from '../components/base-date-picker.vue'
import SubmitButton from '../components/submit-button.vue'

export default {
  name: 'EForm',
  components: {
    BaseInput,
    BasedDropdown,
    BaseDatePicker,
    SubmitButton,
  },
  data() {
    return {
      contents: {
        fullName: {
          title: 'ชื่อ-นามสกุล',
          maxlength: '85',
        },
        lineId: {
          title: 'Line ID',
          maxlength: '30',
        },
        contactNumber: {
          title: 'เบอร์โทร',
          maxlength: '10',
        },
        email: {
          title: 'E-Mail',
          maxlength: '60',
        },
        product: {
          title: 'แผนที่ต้องการ',
          placeholder: 'เลือกแผนที่ต้องการ',
        },
        dealDate: {
          title: 'วันที่สะดวกในการติดต่อ',
        },
        dealTime: {
          title: 'เวลา',
          placeholder: 'เลือกเวลาที่สะดวก',
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
      listTime: [
        { value: 'before9', title: 'ก่อน 9.00 น.' },
        { value: '10to12', title: 'ระหว่าง 10.00 น. - 12.00 น.' },
        { value: '12to13', title: 'ระหว่าง 12.00 น. - 13.00 น.' },
        { value: '13to15', title: 'ระหว่าง 13.00 น. - 15.00 น.' },
        { value: 'after18', title: 'หลัง 18.00 น.' },
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
