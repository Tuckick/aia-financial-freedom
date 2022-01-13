<template>
  <div>
    <div v-for="(item, index) in items" :key="index" class="card-container">
      <img
        :src="require(`~/assets/image/productsNservices/${item.img}.jpg`)"
        alt="item.thTitle"
        class="image-card"
      />
      <div class="card-detail">
        <h3>{{ item.engTitle }}</h3>
        <strong>{{ item.thTitle }}</strong>
        <p>{{ item.desc }}</p>
      </div>
      <Devide />
      <Button :text="btnText" />
    </div>
  </div>
</template>
<script>
import Devide from '../../devide.vue'
import Button from '../../button.vue'

export default {
  name: 'Card',
  components: {
    Devide,
    Button,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      btnText: 'View More',
    }
  },
}
</script>
<style lang="scss" scoped>
@import '~assets/scss/variables';

.card-container {
  max-width: 300px;
  border: 2px solid $dark-gray;
  border-radius: 16px;
  box-shadow: 8px 8px 20px grey;
  padding: 16px;
  text-align: left;
  margin-top: 16px;
  .image-card {
    width: 100%;
    height: inherit;
  }
  .card-detail {
    h3 {
      font-size: $regular;
      margin: 16px auto 0;
    }
    p {
      font-size: $small;
      color: $gray-desc;
    }
  }
}
</style>
