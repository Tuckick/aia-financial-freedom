<template>
  <div class="settings">
    <BaseLabel :title="title" />
    <DatePicker ref="datepicker" :placeholder="placeholder" />
  </div>
</template>

<script>
import BaseLabel from '../components/base-label.vue'

export default {
  name: 'BaseDatePicker',
  components: {
    BaseLabel,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    placeholder: {
      type: String,
      required: false,
      default: 'เลือกวันที่สะดวกในการติดต่อ',
    },
  },
  data() {
    return {
      selectedDate: '',
    }
  },
  method: {
    onChange() {
      this.selectedDate = this.$refs.datepicker.pickedValue
    },
  },
}
</script>
<style lang="scss">
@import '~assets/scss/variables';

input,
select {
  width: 100%;
  height: 40px;
  font-size: $small;
  color: $light-gray;
  float: none;
  display: inline-block;
  box-sizing: border-box;
  border-radius: 4px;
  border: 1px solid $light-gray;
  margin: 4px auto 16px;
  padding: 8px;
}
</style>
