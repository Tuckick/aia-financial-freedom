<template>
  <div class="why-us-container">
    <UnborderCard :items="contents" />
  </div>
</template>
<script>
import UnborderCard from '../../unborder-card.vue'
import WhyUsData from '../../../content/whyUs.json'

export default {
  name: 'WhyUs',
  components: {
    UnborderCard,
  },
  data() {
    return {
      contents: WhyUsData,
    }
  },
}
</script>
