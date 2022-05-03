<template>
  <div class="relative">
    <section id="sec4">
      <div
        class="s4boxp"
        data-aos="fade-left"
        data-aos-duration="1600"
        data-aos-delay="0"
        data-aos-once="false"
      >
        <swiper :options="swiperOptions4" ref="swipers4">
          <swiper-slide v-for="(item, i) in swipList" :key="'s4' + i">
            <div class="s4item">
              <div class="s4tx">{{ item }}</div>
            </div>
          </swiper-slide>
          <template v-slot:button-prev>
            <div class="swiper-button-prev s4pv" @click="prevBtns4"></div>
          </template>
          <template v-slot:button-next>
            <div class="swiper-button-next s4pv" @click="nextBtns4"></div>
          </template>
          <template v-slot:pagination>
            <div class="swiper-pagination"></div>
          </template>
        </swiper>
      </div>
      <div class="s4boxt">
        <div class="s4deco">
          <div
            class="s4t transorileft"
            data-aos="zoom-in"
            data-aos-duration="1600"
            data-aos-delay="100"
            data-aos-once="false"
          >
            全方位 核心商圈
          </div>
          <div
            class="s4s transorileft"
            data-aos="zoom-in"
            data-aos-duration="1600"
            data-aos-delay="200"
            data-aos-once="false"
          >
            雙陽面交匯、動能軸帶
          </div>
          <div
            class="s4p transorileft"
            data-aos="zoom-in"
            data-aos-duration="1600"
            data-aos-delay="300"
            data-aos-once="false"
          >
            捷運站290米(步行3~5分鐘)，6.6萬坪運動公園(步行3~4分鐘)，方圓500m內14家金融機構，星巴克、全家超商、7-11、全聯、區公所、郵局、新莊國中小，隨處皆是生活日常風景，處處是驚喜。
          </div>
        </div>
        <ul class="s4dot">
          <li
            v-for="item in 5"
            :key="'dot' + item"
            @click="fnDotChange(item)"
          ></li>
          <!-- :class="[{ active: dotNow === item }]" -->
        </ul>
      </div>
      <!-- deco vv -->
      <div
        class="s4moon"
        data-aos="zoom-in"
        data-aos-duration="1600"
        data-aos-delay="0"
        data-aos-once="false"
      >
        <div>
          <img src="./all/logobg.png" class="pm" />
          <img src="./all/bird1.png" class="pb" />
        </div>
      </div>
      <div
        class="s4tree"
        data-aos-once="false"
        data-aos="fade-left"
        data-aos-duration="1600"
        data-aos-delay="0"
      >
        <img src="./all/tree1.png" class="treeAni" />
      </div>
    </section>
  </div>
</template>

<script>
import { isMobile, isTablet } from '@/utils'
import $ from 'jquery'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
  components: {
    Swiper,
    SwiperSlide
  },

  computed: {
    // dotNow() {
    //   return 1
    // }
  },

  data() {
    return {
      isMobile,
      isTablet,
      swipList: [
        '新莊捷運站',
        '新莊運動公園',
        '中正路星巴克',
        '新莊國中',
        '新莊國小'
      ],
      swiperOptions4: {
        loop: true, // 是否 slide 後循環
        // initialSlide: 0, // 最初 pic index
        // slidesPerView: 'auto',
        spaceBetween: 0,
        autoplay: {
          delay: 1500,
          disableOnInteraction: false // 換頁後是否停止 autoplay
        },
        speed: 1600,
        grabCursor: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
          type: 'bullets'
        },
        on: {
          slideChangeTransitionEnd: function() {
            // console.log(this.activeIndex) // 切換結束時，告訴我現在是第幾個slide
          },
          slideChangeTransitionStart: function() {
            let eq = this.activeIndex
            // console.log(eq)
            if (eq >= 5) {
              eq = eq - 5
            }
            // console.log(eq) // 切換啟動前，告訴我現在是第幾個slide
            $('.s4dot li')
              .removeClass('active')
              .eq(eq)
              .addClass('active')
          }
        }
      }
    }
  },
  methods: {
    prevBtns4() {
      this.$refs.swipers4.$swiper.slidePrev()
    },
    nextBtns4() {
      this.$refs.swipers4.$swiper.slideNext()
    },
    fnDotChange(i) {
      let eq = i - 1
      // console.log(eq)
      if (eq >= 5) {
        eq = eq - 5
      }
      // console.log(eq)
      this.$refs.swipers4.$swiper.slideTo(eq)
    }
  }
}
</script>

<style lang="sass" scoped>
@import "src/assets/style/myvar"
// 上下頁
.swiper-button-prev,
.swiper-button-next
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
  &:nth-child(1), &:nth-child(6)
    background-image: url('./4/5.jpg')

  &:nth-child(2), &:nth-child(7)
    background-image: url('./4/1.jpg')

  &:nth-child(3), &:nth-child(8)
    background-image: url('./4/2.jpg')

  &:nth-child(4)
    background-image: url('./4/3.jpg')

  &:nth-child(5)
    background-image: url('./4/4.jpg')

// 總高
@media screen and (min-width: $bp-pc)
  .swiper-container, // height 1
  .swiper-wrapper,
  .swiper-slide,
  .s4item
    height: 41.25vw
    // max-height: 70vh
@media screen and (max-width: $bp-mb) and (orientation: portrait)
  .swiper-container,
  .swiper-wrapper,
  .swiper-slide,
  .s4item
    height: 75vw

@media screen and (max-width: $bp-mb) and (orientation: landscape)
  .swiper-container,
  .swiper-wrapper,
  .swiper-slide,
  .s4item
    height: 100vh

// --------------------------------
// -- 我內部介面
// --------------------------------
.s4item
  position: relative

.s4tx
  font:
    size: 20px
    weight: bold
  line-height: 1.7
  position: absolute
  right: .5em
  bottom: .3em
  color: #fff
  text-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5), 0px 0px 5px rgba(0, 0, 0, 0.5)
@media screen and (max-width: $bp-mb)
  .s4tx
    font:
      size: 12px


// --------------------------------
// -- by case customize
// --------------------------------
#sec4

.s4boxp

.s4boxt
  display: flex
  flex-direction: column

@media screen and (min-width: $bp-pc)
  #sec4
    overflow: hidden
    padding: 7vw 0
  .s4boxp
    width: 55vw
    height: 41.25vw // w * 0.75 // height 2
    float: left
  .s4boxt
    float: right
    width: 40vw
    padding-right: 5vw
    justify-content: flex-end
    height: 41.25vw
@media screen and (max-width: $bp-mb)
  #sec4
    display: flex
    flex-direction: column
  .s4boxp
    order: 2

  .s4boxt
    order: 1

// right msg
.s4deco
  @include liinCircle
  &:before
    left: 0
    top: 7px
  &:after
    width: 1px
    top: 8px
    bottom: 0
    left: 2px

.s4boxt
  position: relative
  z-index: 1
  @extend %textShadow

$pl: 40px
.s4deco
  padding-left: $pl
  margin-bottom: 40px
  position: relative
  color: #fff
  display: flex
  align-items: flex-start
  flex-direction: column
  text-align: left

.s4t
  font-size: 18px

.s4s
  margin: 20px 0 40px
  font:
    size: 32px
    weight: 700

.s4p
  font-size: 18px
  line-height: 1.7

@media screen and (min-width: $bp-pc)
  .s4boxt
    padding-bottom: 7.5vw
@media screen and (max-width: $bp-mb)
  .s4boxt
    margin: 20vw 6vw 0

  $pl: 10vw
  .s4deco
    padding-left: $pl
    margin-bottom: 30vw

  .s4t
    font-size: 16px

  .s4s
    margin: 18px 0 35px
    font-size: 23px

  .s4p
    font-size: 16px
    line-height: 1.7

// dot
@media screen and (min-width: $bp-pc)
  .s4dot
    @include swiperCustomDot
    margin-left: calc( #{$pl} - 8px )
    width: 100px
@media screen and (max-width: $bp-mb)
  .s4dot
    display: none

// moon
$mw: 22vw
.s4moon
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
  .s4moon
    width: $mw
    height: $mw

// --------------------------------
// tree
.s4tree
  position: absolute
  z-index: 3
  right: 0
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .s4tree
    width: 21.5vw
    bottom: -0.5vw

@media screen and (max-width: $bp-mb)
  .s4tree
    width: 50vw
    bottom: 68vw
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

// ???
// #s4 {
//   .swiper-container-horizontal > .swiper-pagination-bullets {
//     bottom: auto;
//     top: 999px;
//   }
// }

// @media screen and (max-width: $bp-mb) {
// ??
// #s4 {
//   .swiper-container-horizontal > .swiper-pagination-bullets {
//     display: none;
//   }
// }
</style>
