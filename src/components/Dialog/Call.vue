<template>
  <div class="dialog-content">
    <font-awesome-icon icon="phone" />
    <div class="dialog-desc">賞屋專線</div>
    <div class="info">{{phone}}</div>
    <div class="cta" @click="redirectToPhoneThanks" v-if="isMobile">撥打電話</div>
  </div>
</template>

<script>
import { isMobile } from '@/utils'
export default {
  name: 'CallDialog',
  components: {},
  props: ['phone'],
  data() {
    return {
      isMobile
    }
  },

  methods: {
    redirectToPhoneThanks(e) {
      e.preventDefault()
      window.location.href = `tel:${this.phone.replace('-', '')}`
      setTimeout(() => {
        window.location.href = 'phoneThanks'
      }, 1000)
    },
  },
}
</script>
