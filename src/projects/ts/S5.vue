<template>
  <div class="relative">
    <section id="sec5">
      <div class="s5boxt">
        <div
          class="s5t"
          data-aos="zoom-in transorileft"
          data-aos-duration="800"
          data-aos-delay="0"
          data-aos-once="false"
        >
          至高尊榮 崗石城堡
        </div>
        <div
          class="s5s transorileft"
          data-aos="zoom-in"
          data-aos-duration="1200"
          data-aos-delay="0"
          data-aos-once="false"
        >
          拔高103米、擎天雄姿樓群
        </div>
        <div
          class="s5p transorileft"
          data-aos="zoom-in"
          data-aos-duration="1800"
          data-aos-delay="0"
          data-aos-once="false"
        >
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
        <div class="s5boxPre" @click="prevBtnS5"><b></b></div>
        <div class="s5boxNex" @click="nextBtnS5"><b></b></div>
        <swiper :options="swiperOptionS5s" ref="swiperS5pre" class="isSwPrev">
          <swiper-slide v-for="item in 5" :key="'s5s' + item" loading="lazy" class="swiper-lazy"> </swiper-slide>
        </swiper>
        <!-- main vvv -->
        <swiper :options="swiperOptionS5" ref="swiperS5" class="isSwMain">
          <swiper-slide v-for="item in 5" :key="'s5' + item" loading="lazy" class="swiper-lazy"> </swiper-slide>
        </swiper>
        <!-- main ^^^ -->
        <swiper :options="swiperOptionS5s" ref="swiperS5nex" class="isSwNext">
          <swiper-slide v-for="item in 5" :key="'s5s' + item" loading="lazy" class="swiper-lazy"> </swiper-slide>
        </swiper>
        <div class="s5tx">現場實景</div>
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
      vm: this,
      isMobile,
      isTablet,
      swiperOptionS5s: {
        loop: true,
        lazy: {
          loadPrevNext: true,
        },
        autoplay: {
          delay: 4000,
          disableOnInteraction: false
        },
        speed: 800
      },
      swiperOptionS5: {
        loop: true,
        lazy: {
          loadPrevNext: true,
        },
        autoplay: {
          delay: 4000,
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

  mounted() {
    let xStr = 0
    let xEnd = 0
    const area = 10
    $('.s5boxp').on('touchstart', e => {
      xStr = e.targetTouches[0].pageX
    })
    $('.s5boxp').on('touchmove', e => {
      xEnd = e.targetTouches[0].pageX - xStr
    })
    $('.s5boxp').on('touchend', e => {
      if (xEnd > area) {
        this.prevBtnS5()
      } else if (xEnd < area * -1) {
        this.nextBtnS5()
      }
    })
  },

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
.s5tx
  font:
     size: 14px
  line-height: 1.7
  position: absolute
  left: 50%
  transform: translateX(-50%)
  bottom: .8em
  color: #fff
  z-index: 9
  text-shadow: 0 0 0.55em rgba(0,0,0,1), 0 0 0.2em rgba(0,0,0,1)


@media screen and (min-width: $bp-pc)
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 55.6875vw // w * 1.6875

  // w
  .swiper-container
    &.isSwPrev
      width:  32.9% // height
    &.isSwMain
      width:  42%
    &.isSwNext
      width:  25% // height

  // gurter
  .s5boxp
    // padding-left: .1vw
  


@media screen and (max-width: $bp-mb)
  // h
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 107vw // w * 1.6875

  // w
  .swiper-container
    &.isSwPrev, &.isSwNext
      width: 10vw // height
    &.isSwMain
      width: 80vw

  // gurter
  .s5boxp
    position: relative
    // padding-left: .5vw
    
  .s5tx
    font:
      size: 12px

// --------------------------------
// PRE NEX
.s5boxp
  position: relative

.s5boxPre, .s5boxNex
  display: block
  position: absolute
  width: 30px
  height: 30px
  z-index: 3
  b
    display: block
    width: 100%
    height: 100%
    border: solid 7px #fff
    cursor: pointer

$lr: 3.1vw
.s5boxPre
  left: $lr
  b
    border-width: 5px 5px 0 0
    transform: rotate(225deg)

.s5boxNex
  right: $lr
  b
    border-width: 5px 5px 0 0
    transform: rotate(45deg)

@media screen and (min-width: $bp-pc)
  .s5boxPre, .s5boxNex
    bottom: 5vw

  $lr: 5vw
  .s5boxPre
    left: $lr
    b
      border-width: 5px 5px 0 0

  .s5boxNex
    right: $lr
    b
      border-width: 5px 5px 0 0

@media screen and (max-width: $bp-mb)
  .s5boxPre, .s5boxNex
    top: 50%
    transform: translateY(-50%)

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
  @extend %textShadow
  & > *
    color: #fff

.s5s
  font:
   size: 1.7vw
   weight: 700
  padding: 1.5vw 0 2.5vw

@media screen and (min-width: $bp-pc)
  .s5boxt
    width: 23vw
    top: 20vw
    left: 5vw
    position: absolute
    z-index: 3

  .s5t
    font-size: 15px

  .s5p
    font-size: 18px
    line-height: 1.7
@media screen and (max-width: $bp-mb)
  .s5boxt
    padding: 20vw 8vw 12vw

  .s5t
    font-size: 15px

  .s5s
    font:
     size: 6.4vw
     weight: 700
    padding: 5vw 0 10vw

  .s5p
    font-size: 15px
    line-height: 1.7
</style>
