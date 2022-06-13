<template>
  <div class="relative">
    <section id="sec2">
      <div class="s2video">
        <iframe
          width="560"
          height="315" loading="lazy"
          src="https://www.youtube.com/embed/2cWKFrtwTRs?playlist=2cWKFrtwTRs&loop=1&autoplay=1&controls=0&mute=1&rel=0"
          frameborder="0"
          allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </section>
  </div>
</template>

<style lang="sass">
@import "src/assets/style/myvar"
.s2video
  position: relative
  padding-bottom: 56.25%
  height: 0
  overflow: hidden
  max-width: 100%
  iframe,
  object,
  embed
    position: absolute
    top: 0
    left: 0
    width: 100%
    height: 100%

@media screen and (min-width: $bp-pc)
  .s2video
    pointer-events: none
@media screen and (max-width: $bp-mb)
</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'

export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      isTablet
    }
  },

  methods: {},

  created() {},

  mounted() {},

  computed: {}
}
</script>
