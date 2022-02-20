<template>
  <div class="grid-card">
    <div v-for="(item, index) in items" :key="index" class="card-container">
      <img
        :src="require(`~/assets/image/productsNservices/${item.name}.jpg`)"
        alt="item.thTitle"
        class="image-card"
      />
      <div class="card-detail">
        <h3>{{ item.engTitle }}</h3>
        <strong>{{ item.thTitle }}</strong>
        <p>{{ item.desc }}</p>
      </div>
      <Devide />
      <nuxt-link
        :to="{
          path: '/ProductsAndServices',
          hash: item.name,
        }"
      >
        <Button :text="btnText" />
      </nuxt-link>
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
.grid-card {
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
      height: 190px;
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
  .card-container:last-child {
    margin-bottom: 48px;
  }

  @media (min-width: $desktop-start) and (max-width: $desktop) {
    display: grid;
    grid-gap: 10px;
    grid-template-columns: 300px 300px;
    place-content: center;
    margin-bottom: 48px;

    .card-container:last-child {
      margin-bottom: 0px;
    }
  }

  @media (min-width: $desktop-over) {
    display: grid;
    grid-gap: 10px;
    grid-template-columns: 300px 300px 300px;
    place-content: center;
    margin-bottom: 48px;

    .card-container:last-child {
      margin-bottom: 0px;
    }
  }
}
</style>
