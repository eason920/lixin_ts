<template>
  <div class="relative">
    <section id="sec9">
      <div class="s9boxt">
        <div
          class="s9t"
          data-aos="zoom-in"
          data-aos-duration="800"
          data-aos-once="false"
        >
          東方哲學 西方思想
        </div>
        <div
          class="s9s"
          data-aos="zoom-in"
          data-aos-duration="800"
          data-aos-once="false"
        >
          十邑設計-涵碧樓 設計團隊
        </div>
        <div
          class="s9p transorileftTop"
          data-aos="zoom-in"
          data-aos-duration="800"
          data-aos-once="false"
        >
          攜手豪宅美學巨擘-十邑設計，鑄就精品飯店生活，規劃中西交融設計概念。事業成功、家庭圓滿、生活精彩，才是真正的成功人生！因應回家社交、回家休閒趨勢，除了居住，更要享受，進門就像在飯店Villa度假，重新發現「家」的奧妙。
        </div>
      </div>
      <div class="s9boxp">
        <div
          class="s9pic"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-duration="800"
          data-aos-delay="0"
        >
          <img src="./9/1.jpg" alt="十邑設計-王勝正設計師" loading="lazy" />
          <span>十邑設計<br><br>王勝正設計師</span>
        </div>
      </div>
      <div
        class="s9tree"
        data-aos-once="false"
        data-aos="fade-left"
        data-aos-duration="2000"
        data-aos-delay="0"
      >
        <img src="./all/tree1.png" loading="lazy" class="treeAni" />
      </div>
      <div class="s9moon">
        <img
          src="./all/logobg.png"
          class="moon" loading="lazy"
          data-aos="zoom-in"
          data-aos-duration="2000"
          data-aos-once="false"
        />
        <img
          src="./all/bird1.png"
          class="bird" loading="lazy"
          data-aos="zoom-in"
          data-aos-duration="2400"
          data-aos-once="false"
        />
      </div>
    </section>
  </div>
</template>

<script>
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

<style lang="sass" scoped>
@import "src/assets/style/myvar"
// --------------------------------
// STRUC
#sec9

@media screen and (min-width: $bp-pc)
  #sec9
    padding: 7vw 9vw 13vw
    display: flex
    justify-content: space-between
@media screen and (max-width: $bp-mb)
  #sec9
    padding: 16vw 0 35vw
// --------------------------------
// BOX TXT
.s9t
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

.s9boxt
  display: flex
  align-items: flex-start
  text-align: left
  flex-direction: column
  color: #fff

.s9p
  text-align: justify

@media screen and (min-width: $bp-pc)
  .s9boxt
    width: 28vw
    padding-top: 12vw

  .s9t
    font-size: 15px

  .s9s
    font:
      size: 2vw
      weight: 700
    padding: 1.5vw 0 2.5vw

  .s9p
    width: 90%
    font-size: 18px
    line-height: 1.7

@media screen and (max-width: $bp-mb)
  .s9boxt
    padding: 0 8vw 8vw

  .s9t
    font-size: 15px

  .s9s
    font:
      size: 6vw
      weight: 700
    padding: 4vw 0 7vw

  .s9p
    font-size: 15px
    line-height: 1.7

// --------------------------------
// BOX PIC
.s9boxp

.s9pic
  position: relative
  &:before
    content: ''
    position: absolute
    width: 100%
    height: 100%
    background: #fff
    opacity: .2
  img
    position: relative
    z-index: 1
    width: 100%
  span
   position: absolute
   top: calc(50% - 7.5em)
   right: 1.5em
   color: #fff
   width:1em
   text-align: center
   z-index: 4
   line-height: 1.35
   font: 
    size:100vw * 24 / 1920
    weight: 700

@media screen and (min-width: $bp-pc)
  .s9boxp
    padding-right: 14vw
  .s9pic
    width: 30vw
    &:before
      top: 4vw
      left: 3vw
      border-radius: 15vw
    img
      border-radius: 15vw

@media screen and (max-width: $bp-mb)
  .s9boxp
    padding-left: 8vw
  .s9pic
    width: 62vw
    &:before
      top: 4vw
      left: 3vw
      border-radius: 31vw
    img
      border-radius: 31vw
    span
      font: 
        size:100vw * 12 / 375

// --------------------------------
// tree
.s9tree
  position: absolute
  z-index: 3
  right: 0
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .s9tree
    width: 28vw
    bottom: 1.3vw
@media screen and (max-width: $bp-mb)
  .s9tree
    width: 52vw
    bottom:15vw

// --------------------------------
// MOON
.s9moon,
.bird
  position: absolute
  position: absolute

.moon
  width: 100%
.bird
  width: 50%
  top: 0
  right: 0
@media screen and (min-width: $bp-pc)
  .s9moon
    width: 9vw
    right: 13vw
    bottom: 20vw
@media screen and (max-width: $bp-mb)
  .s9moon
    width: 23vw
    right: 6vw
    bottom: 45vw
</style>
