<template>
  <div class="relative">
    <section id="sec8">
      <div class="s8boxt">
        <span data-aos="fade-up" data-aos-duration="800" data-aos-once="false"
          >稀珍挑高4.2米 精品宅</span
        >
        <p data-aos="fade-up" data-aos-duration="1600" data-aos-once="false">
          城市核心稀珍挑高4.2米精品宅，走外樑外柱、淨空間規劃，四面採光，舒適宜居的人性化尺度布局，生活有餘裕、時尚即日常，享樂型優質資產。
        </p>
      </div>
      <div class="s8boxp">
        <swiper :options="swiperOptions8" ref="swipers8"
        @mouseenter.native="mouseEnter"
        @mouseleave.native="mouseLeave">
          <swiper-slide v-for="(item, i) in swipList" :key="'s8' + i">
            <div class="s8item">
              <div class="s8tx">{{ item }}</div>
            </div>
          </swiper-slide>
          <template v-slot:button-prev>
            <div class="swiper-button-prev s8pv" @click="prevBtns8"></div>
          </template>
          <template v-slot:button-next>
            <div class="swiper-button-next s8pv" @click="nextBtns8"></div>
          </template>
          <template v-slot:pagination>
            <div class="swiper-pagination"></div>
          </template>
        </swiper>
        <ul class="s8sw">
          <li
            :class="[{ active: i === current }]"
            v-for="(item, i) in dotList"
            :key="'sw' + i"
            @click="fnSW(i)"
          >
            {{ item }}
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
import { isMobile, isTablet } from '@/utils'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'
import $ from 'jquery'
let page = 0

export default {
  components: {
    Swiper,
    SwiperSlide
  },

  data() {
    return {
      isMobile,
      isTablet,
      swipList: [
        '24坪-樣品屋實拍圖',
        '24坪-樣品屋實拍圖',
        '24坪-樣品屋實拍圖',
        '39坪-樣品屋實拍圖',
        '39坪-樣品屋實拍圖',
        '39坪-樣品屋實拍圖',
        '65坪-樣品屋實拍圖',
        '65坪-樣品屋實拍圖',
        '65坪-樣品屋實拍圖'
      ],
      dotList: ['24坪', '39坪', '65坪'],
      current: 2,
      swiperOptions8: {
        loop: true,
        // initialSlide: 0, // 最初 pic index
        // slidesPerView: 'auto',
        spaceBetween: 0,
        autoplay: {
          delay: 2500,
          disableOnInteraction: false, // 換頁後是否停止 autoplay
          stopOnLastSlide: false,
        },
        speed: 800,
        grabCursor: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
          type: 'bullets'
        },
        on: {
          slideChangeTransitionStart: function() {
            let eq = this.activeIndex
         //   console.log(eq)
            switch (eq) {
              case 1:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(0)
                  .addClass('active')
                break
              case 4:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(1)
                  .addClass('active')
                break
              case 7:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(2)
                  .addClass('active')
                break
              case 10:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(0)
                  .addClass('active')
                break
              case 3:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(0)
                  .addClass('active')
                break
              case 6:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(1)
                  .addClass('active')
                break
              case 9:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(2)
                  .addClass('active')
                break
              case 0:
                $('.s8sw li').removeClass('active')
                $('.s8sw li')
                  .eq(2)
                  .addClass('active')
                break
              default:
            }
          },
          slideChangeTransitionEnd: function() {
            // let eq = this.activeIndex
          }
        }
      }
    }
  },
  methods: {
    mouseEnter() { 
      this.$refs.swipers8.$swiper.autoplay.stop();
    },
    mouseLeave() { 
      this.$refs.swipers8.$swiper.autoplay.start();
    },
    prevBtns8() {
      this.$refs.swipers8.$swiper.slidePrev()
    },
    nextBtns8() {
      this.$refs.swipers8.$swiper.slideNext()
    },
    fnDotChange(i) {
      let eq = i - 1
      // console.log(eq)
      if (eq >= 5) {
        eq = eq - 5
      }
      // console.log(eq)
      this.$refs.swipers8.$swiper.slideTo(eq)
    },
    fnSW(i) {
  //   console.log(i)
      this.current = i
      let eq = 1
      switch (i) {
        case 0:
          eq = 1
          break
        case 1:
          eq = 4
          break
        case 2:
          eq = 7
          break
        default:
      }
      this.$refs.swipers8.$swiper.slideTo(eq)
    }
  },

  created() {},

  mounted() {},

  computed: {}
}
</script>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
// 上下頁
.swiper-button-prev,
.swiper-button-next
  -webkit-tap-highlight-color: transparent
  width: 50px
  height: 80px
  &:after
    color: #fff
    text-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5), 0px 0px 5px rgba(0, 0, 0, 0.5)

@media screen and (max-width: $bp-mb)
  .swiper-button-prev,
  .swiper-button-next
    width: 30px !important
    top: 50%
    transform: translateY(-20%)
    &:after
      font-size: 32px

// 圖片
.swiper-slide
  background:
    position: center
    size: cover
  &:nth-child(1), &:nth-child(10)
    background-image: url('./8/9.jpg')

  &:nth-child(2), &:nth-child(11)
    background-image: url('./8/1.jpg')

  &:nth-child(3), &:nth-child(12)
    background-image: url('./8/2.jpg')

  &:nth-child(4)
    background-image: url('./8/3.jpg')

  &:nth-child(5)
    background-image: url('./8/4.jpg')

  &:nth-child(6)
    background-image: url('./8/5.jpg')

  &:nth-child(7)
    background-image: url('./8/6.jpg')

  &:nth-child(8)
    background-image: url('./8/7.jpg')

  &:nth-child(9)
    background-image: url('./8/8.jpg')

// 總高
.swiper-container
  &:before, &:after
    content: ""
    position: absolute
    top: 0
    width: 10vw
    height: 100%
    z-index: 9
  &:before
    background-image: linear-gradient(to left, rgba(255,255,255, 0), #fff)
    left: 0
  &:after
    background-image: linear-gradient(to right, rgba(255,255,255, 0), #fff)
    right: 0

.swiper-container, // height 1
.swiper-wrapper,
.swiper-slide,
.s8item
  height: 56.25vw
@media screen and (min-width: $bp-pc)

// --------------------------------
// -- 我內部介面
// --------------------------------
.s8item
  position: relative

.s8tx
  font:
    size: 14px
  height: 30px
  position: absolute
  right: 4vw
  bottom: 1.7vw
  color: #fff
  @extend %textShadowDeep

@media screen and (max-width: $bp-mb)
  .s8tx
    // display: none

// --------------------------------
// -- by case customize
// --------------------------------
// OUTER
@media screen and (min-width: $bp-pc)
  #sec8
    // padding: 7vw 0

@media screen and (max-width: $bp-mb)
  #sec8
    display: flex
    flex-direction: column

// --------------------------------
// TXT BOX
.s8boxt
  background: #E95513
  display: flex
  flex-direction: column
  align-items: center
  position: relative
  z-index: 10
  color: #fff

  span
    position: relative
    display: block
    width: 100%
    &:before, &:after
      content: ''
      position: absolute
      height: 1px
      background: #fff
    &:before
      left: 0
    &:after
      right: 0

@media screen and (min-width: $bp-pc)
  .s8boxt
    padding-top: 3vw
    padding-bottom: 4vw

    span
      font:
        size: 42px
        weight: 700
      padding-bottom: 1vw
      width: 100%
      &:before, &:after
        top: 20px
        width: calc( 50vw - 300px)
    p
      font-size: 16px
      line-height: 1.5
      width: 50vw
@media screen and (max-width: $bp-mb)
  .s8boxt
    padding-top: 13vw
    padding-bottom: 15vw

    span
      font:
        size: 24px
        weight: 700
      padding-bottom: 7vw
      width: 100%
      &:before, &:after
        top: 13px
        width: 10vw
    p
      font-size: 16px
      line-height: 1.5
      width: 86vw

// --------------------------------
// PIC BOX
.s8boxp
  width: 100vw
  height: 56.25vw // w * 0.5625 // height 2

// right msg
.s8deco
  @include liinCircle
  &:before
    left: 0
    top: 7px
  &:after
    width: 1px
    top: 8px
    bottom: 0
    left: 2px

$pl: 40px
.s8deco
  padding-left: $pl
  margin-bottom: 40px
  position: relative
  color: #fff
  display: flex
  align-items: flex-start
  flex-direction: column
  text-align: left

.s8t
  font-size: 18px

.s8s
  font-size: 32px
  margin: 20px 0 40px
  @extend %textShadow

.s8p
  font-size: 18px
  line-height: 1.7
  @extend %textShadow

@media screen and (max-width: $bp-mb)
  $pl: 10vw
  .s8deco
    padding-left: $pl
    margin-bottom: 30vw

  .s8t
    font-size: 16px

  .s8s
    font-size: 23px
    margin: 18px 0 35px

  .s8p
    font-size: 16px
    line-height: 1.7

// moon
$mw: 22vw
.s8moon
  width: $mw
  height: $mw
  right: 2vw
  top: 6vw
  position: absolute
  div
    position: relative
.pm
  width: 100%

.pb
  width: 45%
  position: absolute
  top: 6.5vw
  right: 0

@media screen and (min-width: $bp-pc)
@media screen and (max-width: $bp-mb)
  $mw: 40vw
  .s8moon
    width: $mw
    height: $mw

// --------------------------------
// SWITCH
.s8boxp
  position: relative
.s8sw
  position: absolute
  box-shadow: 0 0 12px rgba(0,0,0,.7), 0 0 12px rgba(0,0,0,.7)
  background: #fff
  display: flex
  left: 50%
  transform: translateX(-50%)
  z-index: 11
  li
    outline: none
    display: flex
    align-items: center
    cursor: pointer
    &.active
      cursor: default
      background: #E95513
      color: #fff

@media screen and (min-width: $bp-pc)
  .s8sw
    bottom: 3vw
    height: 40px
    border-radius: 20px
    li
      padding: 0 3vw
      font-size: 18px
      &.active
        border-radius: 30px
@media screen and (max-width: $bp-mb)
  .s8sw
    top: -15px
    height: 30px
    border-radius: 15px
    width: 80vw
    justify-content: space-between
    li
      justify-content: center
      width: 33%
      font-size: 16px
      &.active
        border-radius: 30px
</style>

<style lang="scss">
// ----------------------------
// -- 不可 sass (?!!!!) 也不可 scoped
// ----------------------------
@import 'src/assets/style/myvar';
// 輪撥點點點的顯示 & 美術
.swiper-container-horizontal
  > .swiper-pagination-bullets
  .swiper-pagination-bullet {
  &.swiper-pagination-bullet-active {
    background: #f2f2f2;
  }
}

.swiper-container-horizontal
  > .swiper-pagination-bullets
  .swiper-pagination-bullet {
  display: none;
}
</style>
