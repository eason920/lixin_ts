<template>
  <div class="relative">
    <section id="sec10">
      <div class="s10boxp">
        <swiper :options="swiperOptions10s" ref="swipers10pre" class="isSwPrev">
          <swiper-slide v-for="item in 5" :key="'s10s' + item"> </swiper-slide>
        </swiper>
        <!-- main vvv -->
        <swiper :options="swiperOptions10" ref="swipers10" class="isSwMain">
          <swiper-slide v-for="item in 5" :key="'s10' + item"> </swiper-slide>
        </swiper>
        <!-- main ^^^ -->
        <swiper :options="swiperOptions10s" ref="swipers10nex" class="isSwNext">
          <swiper-slide v-for="item in 5" :key="'s10s' + item"> </swiper-slide>
        </swiper>
      </div>
      <div class="s10boxc">
        <div class="aleft arrow" @click="prevBtns10">
          <img src="../share/arrow_left.png" />
        </div>
        <p class="s10txt">公設示意圖</p>
        <ul v-if="!isMobile" class="s10dot">
          <li
            v-for="item in 5"
            :key="'dot' + item"
            @click="fnDotChange(item)"
          ></li>
        </ul>
        <div class="aright arrow" @click="nextBtns10">
          <img src="../share/arrow_right.png" />
        </div>
      </div>
      <div class="wave">
        <!-- <img src="./S6/wwave.svg" /> -->
        <svg
          version="1.1"
          id="圖層_1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 1700 360"
          style="enable-background:new 0 0 1700 360;transform-origin: 50% 80%"
          xml:space="preserve"
        >
          <linearGradient
            id="Background_00000072963187350370406180000016455295041147087744_"
            gradientUnits="userSpaceOnUse"
            x1="850"
            y1="360"
            x2="850"
            y2="-9.094947e-13"
          >
            <stop offset="0.1863" style="stop-color:#E95513" />
            <stop offset="1" style="stop-color:#E95513;stop-opacity:0" />
          </linearGradient>
          <path
            id="Background_00000073684196276930211830000003937701023396488120_"
            style="fill:url(#Background_00000072963187350370406180000016455295041147087744_);"
            d="M1700,360c-371.3,0-420.7-68-750.6-68S403.4,360,0,360V0h1700V360z"
          />
        </svg>
      </div>
    </section>
  </div>
</template>

<script>
import $ from 'jquery'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

import { isMobile, isTablet } from '@/utils'

let msgAry = ['msg1', 'msg2', 'msg3', 'msg4', 'msg5']

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
      swiperOptions10: {
        loop: true,
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
            $('.s10dot li')
              .removeClass('active')
              .eq(eq)
              .addClass('active')
            $('.s10txt').text(msgAry[eq])
          }
        }
      },
      swiperOptions10s: {
        loop: true,
        autoplay: {
          delay: 1500,
          disableOnInteraction: false
        },
        speed: 800
      }
    }
  },

  methods: {
    prevBtns10() {
      this.$refs.swipers10.$swiper.slidePrev()
      this.$refs.swipers10pre.$swiper.slidePrev()
      this.$refs.swipers10nex.$swiper.slidePrev()
    },
    nextBtns10() {
      this.$refs.swipers10.$swiper.slideNext()
      this.$refs.swipers10pre.$swiper.slideNext()
      this.$refs.swipers10nex.$swiper.slideNext()
    },
    fnDotChange(i) {
      let eq = i - 1
      // console.log(eq)
      if (eq >= 5) {
        eq = eq - 5
      }
      // console.log(eq)
      this.$refs.swipers10.$swiper.slideTo(eq)
      this.$refs.swipers10pre.$swiper.slideTo(eq)
      this.$refs.swipers10nex.$swiper.slideTo(eq)
    }
  },

  created() {},

  mounted() {
    $('.s10txt').text(msgAry[0])
    let xStr = 0
    let xEnd = 0
    const area = 10
    $('.s10boxp').on('touchstart', e => {
      xStr = e.targetTouches[0].pageX
    })
    $('.s10boxp').on('touchmove', e => {
      xEnd = e.targetTouches[0].pageX - xStr
    })
    $('.s10boxp').on('touchend', e => {
      if (xEnd > area) {
        this.prevBtns10()
      } else if (xEnd < area * -1) {
        this.nextBtns10()
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
  pointer-events: none
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(6)
      background-image: url('./10/4.jpg')

    &:nth-child(2), &:nth-child(7)
      background-image: url('./10/5.jpg')

    &:nth-child(3), &:nth-child(8)
      background-image: url('./10/1.jpg')

    &:nth-child(4)
      background-image: url('./10/2.jpg')

    &:nth-child(5)
      background-image: url('./10/3.jpg')

.isSwMain
  pointer-events: none
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(6)
      background-image: url('./10/5.jpg')

    &:nth-child(2), &:nth-child(7)
      background-image: url('./10/1.jpg')

    &:nth-child(3), &:nth-child(8)
      background-image: url('./10/2.jpg')

    &:nth-child(4)
      background-image: url('./10/3.jpg')

    &:nth-child(5)
      background-image: url('./10/4.jpg')

.isSwNext
  pointer-events: none
  .swiper-slide
    background:
      position: center
      size: cover
    &:nth-child(1), &:nth-child(6)
      background-image: url('./10/1.jpg')

    &:nth-child(2), &:nth-child(7)
      background-image: url('./10/2.jpg')

    &:nth-child(3), &:nth-child(8)
      background-image: url('./10/3.jpg')

    &:nth-child(4)
      background-image: url('./10/4.jpg')

    &:nth-child(5)
      background-image: url('./10/5.jpg')

// --------------------------------
// -- by case customize
// --------------------------------
// 架構
#sec10
  position: relative

@media screen and (min-width: $bp-pc)
  #sec10
    padding-bottom: 7vw
@media screen and (max-width: $bp-mb)
  #sec10
    padding-bottom: 15vw
// --------------------------------
// SLIDE SHOW
.s10boxp
  font-size: 0
  overflow: hidden

.swiper-container
  &.isSwMain
    z-index: 2

// w

.isSwPrev,
.isSwNext
  position: absolute
  top: 0
@media screen and (min-width: $bp-pc)
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 39.394vw // w * 0.5627

  .swiper-container
    width: 70vw // height

  .isSwMain
    margin-left: 15vw

  .isSwPrev,
  .isSwNext
    transform: scale(.97)

  .isSwPrev
    left: -56vw
  .isSwNext
    right: -57vw

@media screen and (max-width: $bp-mb)
  .swiper-container, // height
  .swiper-wrapper,
  .swiper-slide
    height: 50.643vw

  .swiper-container
    width: 90vw // height

  .isSwMain
    margin-left: 5vw

  .isSwPrev,
  .isSwNext
    transform: scale(.9)

  .isSwPrev
    left: -82vw
  .isSwNext
    right: -82vw

// --------------------------------
// dot
@media screen and (min-width: $bp-pc)
  .s10dot
    @include swiperCustomDot
    width: 100px

@media screen and (max-width: $bp-mb)
  .s10dot
    display: none

// --------------------------------
// CONTROL BOX
.s10boxc
  display: flex
  align-items: center
  justify-content: space-between
  & > *
    color: #fff

@media screen and (min-width: $bp-pc)
  .s10boxc
    width: 95vw
    margin:
      left: 2.5vw
      top: 2vw

@media screen and (max-width: $bp-mb)
  .s10boxc
    padding: 5vw 5vw 0

// --------------------------------
// arrow
.arrow
  border-radius: 50%
  border: solid 1px #fff
  display: flex
  justify-content: center
  align-items: center
  cursor: pointer
  img
    width: 50%

.s10txt
  font-size: 15px
  @extend %textShadow

@media screen and (min-width: $bp-pc)
  $c: 40px
  .arrow
    width: $c
    height: $c
  .s10txt
    position: absolute
    top: -4.5em
    left: calc(50% - 2.8em)
@media screen and (max-width: $bp-mb)
  $c: 20px
  .arrow
    width: $c
    height: $c

// --------------------------------
// wave
.s10boxp, .s10boxc
  position: relative
  z-index: 97
.wave
  bottom: -8vw
.st0
  fill: url(#Background_00000134238645198909741730000014252396130775589005_)
</style>
