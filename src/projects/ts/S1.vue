<template>
  <div class="relative">
    <section id="sec1">
      <img
        v-if="!isMobile"
        src="./all/bird1.png"
        class="s1bird1"
        data-aos-once="false"
        data-aos="fade-left"
        data-aos-duration="2800"
        data-aos-delay="300"
      />
      <img
        src="./all/bird2.png"
        class="s1bird2"
        data-aos-once="false"
        data-aos="fade-right"
        data-aos-duration="2500"
        data-aos-delay="200"
      />
      <div
        class="s1tree"
        data-aos-once="false"
        data-aos="fade-left"
        data-aos-duration="800"
        data-aos-delay="100"
      >
        <img src="./all/tree1.png" class="treeAni" />
      </div>
      <div class="s1moonOuter">
        <div
          class="s1moon"
          data-aos-once="false"
          data-aos="fade-in"
          data-aos-duration="1200"
          data-aos-delay="0"
        >
          <LOGO />
          <div class="txt">
            <div class="title1" data-aos="fade" data-aos-delay="100">
              24~93坪<span></span>挑高4米2
            </div>
            <div class="title2" data-aos="fade" data-aos-delay="300">
              新莊中正路、新泰路口
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="s1Masker"></div>
  </div>
</template>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
#sec1
  background:
    image: url(./all/mount.png)
    position: center bottom
    repeat: no-repeat
  img
    // height: 100px
.s1moonOuter
  @extend %fullScreen
  background:
    image: url(./all/logobg.png)
    size: cover

.s1moon
  width: 100%
  height: 100%
  display: flex
  flex-direction: column
  align-items: center
  justify-content: center
  svg
   width: 90%

.s1bird1, .s1bird2
  position: absolute
  z-index: 3

.s1tree
  position: absolute
  z-index: 3
  right: 0
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  #sec1
    height: 100vh
    background:
      size: contain

  .s1bird1
    width: 6vw
    top: 28vh
    left: 22vw

  .s1bird2
    width: 18vw
    top: 18vh
    right: 14vw

  $sw: 40vw
  $smw: 550px
  .s1moonOuter
    width: $sw
    height: $sw
    min-width: $smw
    min-height: $smw

  .s1tree
    width: 35.5vw
    bottom: 2.5vw

@media screen and (max-width: $bp-mb)
  #sec1
    height: calc(100vh - 63px )
    min-height: 100vw * 550 / 375
    max-height: 100vw *750 /375
    background:
      size: 100% auto
      position: 50% 75%

  .s1bird2
    width: 40vw
    top: 28vw
    left: 5vw

  $sw: 90vw
  .s1moonOuter
    width: $sw
    height: $sw
  .s1tree
    width: 60vw
    bottom: calc(30% + (15 - 604 * .3) * 100vw / 375)

// --------------------------------
// MASKER
.s1Masker
  @extend %fullScreen
  background-color: #fff
  z-index: 20
  &.start
    animation: maskOut 2s linear forwards

@keyframes maskOut
  0%
    opacity: 1

  20%
    background-color: #f3580e
  100%
    opacity: 0
</style>

<!-- COPY -->
<style lang="scss" scoped>
.txt {
  // @include img_c_pc(1100, 620);
  top: calc(50% + (620 - 540) * 100vw / 1920);
  font-size: calc(34 * 100vw / 1920);
  color: #000;
  font-weight: 700;
  line-height: 1.4;
  z-index: 2;
  letter-spacing: 0.01em;
  .title1 {
    transform: scaleX(5);
    font-size: 1.4em;
    span {
      display: inline-block;
      width: 2px;
      height: 0.8em;
      position: relative;
      margin: 0 0.4em;
      background: currentColor;
    }
  }
  .title2 {
    transform: scaleX(5);
    letter-spacing: 0.06em;
  }
}

@media screen and (max-width: 767px) {
  .txt {
    // @include img_c_m(370, 300);
    top: calc(40% + (300 - 604 * 0.4) * 100vw / 375);
    font-size: calc(16 * 100vw / 375);
  }
}
</style>

<script>
import { isMobile, isTablet } from '@/utils'
import LOGO from '@/projects/ts/logo.vue'
export default {
  name: 'section1',

  components: {
    LOGO
  },

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
