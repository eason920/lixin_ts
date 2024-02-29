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
  <swiper-slide v-for="(item, i) in swipList" :key="'s8' + i" loading="lazy" class="swiper-lazy">
    <div class="s8item">
      <img :src="item.src" :alt="item.name">
      <div class="s8tx">{{ item.name }}</div>
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
        { name: '39坪-樣品屋實拍圖1', src: require('./8/4.jpg')},
        { name: '39坪-樣品屋實拍圖2', src: require('./8/5.jpg')},
        { name: '39坪-樣品屋實拍圖3', src: require('./8/6.jpg')},
        { name: '65坪-樣品屋實拍圖4', src: require('./8/7.jpg')},
        { name: '65坪-樣品屋實拍圖5', src: require('./8/8.jpg')},
        { name: '65坪-樣品屋實拍圖6', src: require('./8/9.jpg')}
      ],
      dotList: ['39坪', '65坪'],
      current: 0,
      swiperOptions8: {
        loop: true,
        lazy: {
          loadPrevNext: true,
        },
        spaceBetween: 0,
        autoplay: {
          delay: 2500,
          disableOnInteraction: false,
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
            let eq = this.activeIndex;
            let buttonIndex = Math.floor((eq - 1) / 3) % 2; // 计算当前图片所在的组索引
            $('.s8sw li').removeClass('active');
            $('.s8sw li').eq(buttonIndex).addClass('active'); // 设置对应组的按钮为亮起状态
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
      this.$refs.swipers8.$swiper.slidePrev();
    },
    nextBtns8() {
      this.$refs.swipers8.$swiper.slideNext();
    },
    fnSW(i) {
      this.current = i;
      const eq = i * 3; // 根据底部按钮索引来计算显示的图片索引
      this.$refs.swipers8.$swiper.slideTo(eq);
    },
    getImageUrl(index) {
      return this.swipList[index].src;
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

  img 
    width: 100%

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
    justify-content: center
    justify-content: space-between
    white-space: nowrap
    li
      justify-content: center
      width: 6em
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
