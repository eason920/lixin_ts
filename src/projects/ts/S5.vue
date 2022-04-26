<template>
  <div class="relative">
    <section id="sec5">
      <div class="s5boxt">
        <div class="s5t">至高尊榮 崗石城堡</div>
        <div class="s5s">拔高103米、擎天雄姿樓群</div>
        <div class="s5p">
          大度領受世人仰望的視角，氣勢磅礡，已然改寫了新莊最精華地段的天際線，崗石鑄造，承襲王族大統從此獨占層峰版圖最醒目的位置。
        </div>
        <ul class="s5dot">
          <li
            v-for="item in 5"
            :key="'dot' + item"
            @click="fnDotChange(item)"
          ></li>
        </ul>
      </div>
      <div class="s5boxp">
        <swiper :options="swiperOptionS5s" ref="swiperS5pre" class="isSwPrev">
          <swiper-slide v-for="item in 5" :key="'s5s' + item"> </swiper-slide>
        </swiper>
        <!-- main vvv -->
        <swiper :options="swiperOptionS5" ref="swiperS5" class="isSwMain">
          <swiper-slide v-for="item in 5" :key="'s5' + item"> </swiper-slide>
        </swiper>
        <!-- main ^^^ -->
        <swiper :options="swiperOptionS5s" ref="swiperS5nex" class="isSwNext">
          <swiper-slide v-for="item in 5" :key="'s5s' + item"> </swiper-slide>
        </swiper>
      </div>
    </section>
  </div>
</template>

<script>
import $ from 'jquery'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

import { isMobile, isTablet } from '@/utils'

export default {
  name: 'swiper-example-thumbs-gallery',
  title: 'Thumbs gallery with Two-way control',
  components: {
    Swiper,
    SwiperSlide
  },

  data() {
    return {
      isMobile,
      isTablet,
      swiperOptionS5: {
        autoplay: {
          delay: 1500,
          disableOnInteraction: false
        },
        speed: 800,
        on: {
          slideChangeTransitionStart: function() {
            let eq = this.activeIndex
            if (eq >= 5) {
              eq = eq - 5
            }
            $('.s5dot li')
              .removeClass('active')
              .eq(eq)
              .addClass('active')
          }
        }
      },
      swiperOptionS5s: {
        autoplay: {
          delay: 1500,
          disableOnInteraction: false
        },
        speed: 800
      }
    }
  },

  methods: {
    prevBtnS5() {
      this.$refs.swiperS5.$swiper.slidePrev()
      this.$refs.swiperS5pre.$swiper.slidePrev()
      this.$refs.swiperS5nex.$swiper.slidePrev()
    },
    nextBtnS5() {
      this.$refs.swiperS5.$swiper.slideNext()
      this.$refs.swiperS5pre.$swiper.slideNext()
      this.$refs.swiperS5nex.$swiper.slideNext()
    },
    fnDotChange(i) {
      let eq = i - 1
      // console.log(eq)
      if (eq >= 5) {
        eq = eq - 5
      }
      // console.log(eq)
      this.$refs.swiperS5.$swiper.slideTo(eq)
      this.$refs.swiperS5pre.$swiper.slideTo(eq)
      this.$refs.swiperS5nex.$swiper.slideTo(eq)
    }
  },

  created() {},

  mounted() {},

  computed: {}
}
</script>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
// 圖片
.isSwPrev
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(6)
      background-image: url('./5/4.jpg')

    &:nth-child(2), &:nth-child(7)
      background-image: url('./5/5.jpg')

    &:nth-child(3), &:nth-child(8)
      background-image: url('./5/1.jpg')

    &:nth-child(4)
      background-image: url('./5/2.jpg')

    &:nth-child(5)
      background-image: url('./5/3.jpg')

.isSwMain
  pointer-events: none
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(6)
      background-image: url('./5/5.jpg')

    &:nth-child(2), &:nth-child(7)
      background-image: url('./5/1.jpg')

    &:nth-child(3), &:nth-child(8)
      background-image: url('./5/2.jpg')

    &:nth-child(4)
      background-image: url('./5/3.jpg')

    &:nth-child(5)
      background-image: url('./5/4.jpg')

.isSwNext
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(6)
      background-image: url('./5/1.jpg')

    &:nth-child(2), &:nth-child(7)
      background-image: url('./5/2.jpg')

    &:nth-child(3), &:nth-child(8)
      background-image: url('./5/3.jpg')

    &:nth-child(4)
      background-image: url('./5/4.jpg')

    &:nth-child(5)
      background-image: url('./5/5.jpg')

.isSwPrev,
.isSwNext
  filter: grayscale(1) brightness(.8) blur(9px)
  pointer-events: none

// @media screen and (max-width: $bp-mb) and (orientation: portrait)
//   .swiper-container,
//   .swiper-wrapper,
//   .swiper-slide
//     height: 30vh

// @media screen and (max-width: $bp-mb) and (orientation: landscape)
//   .swiper-container,
//   .swiper-wrapper,
//   .swiper-slide
//     height: 100vh

// --------------------------------
// -- by case customize
// --------------------------------
// 架構
#sec5
.s5boxp
  font-size: 0
  background-color: #666
  overflow: hidden

.swiper-container
  float: left
  &.isSwMain
    z-index: 2
    box-shadow: 0 0 12px rgba(0,0,0,.5), 0 0 12px rgba(0,0,0,.5)

@media screen and (min-width: $bp-pc)
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 55.6875vw // w * 1.6875

  // w
  .swiper-container
    width: 32.9vw // height

  // gurter
  .s5boxp
    // padding-left: .1vw

@media screen and (max-width: $bp-mb)
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 99.5625vw // w * 1.6875

  // w
  .swiper-container
    &.isSwPrev, &.isSwNext
      width: 20vw // height
    &.isSwMain
      width: 60vw

  // gurter
  .s5boxp
    // padding-left: .5vw

// --------------------------------
// dot
@media screen and (min-width: $bp-pc)
  .s5dot
    @include swiperCustomDot
    width: 100px
    margin-top: 3vw

@media screen and (max-width: $bp-mb)
  .s5dot
    display: none

// --------------------------------
// msg
#sec5
  position: relative

.s5t
  @include liinCircle
  width: 100%
  position: relative
  &:before
    right: 0
    top: 5px
  &:after
    height: 1px
    top: 7px
    right: 0
    left: 150px

.s5boxt
  display: flex
  align-items: flex-start
  text-align: left
  flex-direction: column
  & > *
    color: #fff
    @extend %textShadowDeep

@media screen and (min-width: $bp-pc)
  .s5boxt
    width: 23vw
    top: 20vw
    left: 5vw
    position: absolute
    z-index: 3

  .s5t
    font-size: 15px

  .s5s
    font-size: 1.7vw
    padding: 1.5vw 0 2.5vw

  .s5p
    font-size: 18px
    line-height: 1.7
@media screen and (max-width: $bp-mb)
  .s5boxt
    padding: 20vw 8vw 12vw
  .s5t
    font-size: 15px

  .s5s
    font-size: 6.4vw
    padding: 5vw 0 10vw

  .s5p
    font-size: 18px
    line-height: 1.7
</style>
