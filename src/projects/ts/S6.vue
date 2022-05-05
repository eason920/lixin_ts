<template>
  <div class="relative">
    <section id="sec6">
      <div class="s6boxt">
        <img
          src="./all/logobg.png"
          class="moon"
          data-aos="zoom-in"
          data-aos-duration="4800"
          data-aos-once="false"
        />
        <div class="s6deco">
          <div
            class="s6t transorileft"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false"
          >
            地質改良 磐石工法
          </div>
          <div
            class="s6s transorileft"
            data-aos="zoom-in"
            data-aos-duration="1200"
            data-aos-once="false"
          >
            穩扎地心，深入大地
          </div>
          <div
            class="s6p transorileft"
            data-aos="zoom-in"
            data-aos-duration="1600"
            data-aos-once="false"
          >
            地下層採逆打工法，連續壁達36.5米深，逆打鋼柱基樁就深插至48.7米，相當於一半的地上層深，搭配高壓灌注地質改良，與土層穩扎結合，固化成堅硬柱體，和原地層形成複合作用，提升地盤強度。
          </div>
        </div>
      </div>
      <div class="s6boxp">
        <img
          src="./6/1.jpg"
          data-aos="fade-up"
          data-aos-duration="1200"
          data-aos-once="false"
        />
      </div>
      <div
        class="s6tree"
        data-aos-once="false"
        data-aos="fade-left"
        data-aos-duration="800"
        data-aos-delay="0"
      >
        <img src="./all/tree1.png" class="treeAni" />
      </div>
    </section>
    <section id="sec6-2">
      <div class="s6hr"><b></b></div>
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
// S6
#sec6
  display: flex
#sec6, #sec6-2
  background:
    image: url(./all/bgw.jpg)

@media screen and (min-width: $bp-pc)
  #sec6
    justify-content: space-between
    overflow: hidden

  .s6boxp
    order: 1

  .s6boxt
    order: 2

@media screen and (max-width: $bp-mb)
  #sec6
    display: flex
    flex-direction: column

// --------------------------------
// PIC BOX
.s6boxp

@media screen and (min-width: $bp-pc)
  .s6boxp
    // height: 100vh
    width: 53vw
    text-align: left
    img
      // height: 100%
      width: 100%
    // width: 55vw

@media screen and (max-width: $bp-mb)
  .s6boxp
    width: 88vw
    margin-left: 6vw
    text-align: left
    img
      width: 100%
      height: 155vw
      object-fit: cover

// --------------------------------
// TXT BOX
.s6boxt
  display: flex
  flex-direction: column
  position: relative
  z-index: 1

.s6deco
  @include liinCircle
  &:before, &:after
    background: #000
  &:before
    left: 0
    top: 7px
  &:after
    width: 1px
    top: 8px
    bottom: 0
    left: 2px

$pl: 40px
.s6deco
  padding-left: $pl
  margin-bottom: 40px
  position: relative
  display: flex
  align-items: flex-start
  flex-direction: column
  text-align: left

.s6t
  font-size: 100vw * 18 / 1920

.s6s
  font:
   size: 100vw * 32 / 1920
   weight: 700
  margin: 0.625em 0 1.25em

.s6p
  font-size: 100vw * 18 / 1920
  line-height: 1.7
  text-align: justify


@media screen and (min-width: $bp-pc)
  .s6boxt
    width: 40vw
    padding-right: 5vw
    justify-content: flex-end
    height: 41.25vw
    padding-bottom: 7.5vw
@media screen and (max-width: $bp-mb)
  .s6boxt
    margin: 20vw 6vw 0

  $pl: 5vw
  .s6deco
    padding-left: $pl
    margin-bottom: 25vw

  .s6t
    font-size: 100vw * 16 / 375

  .s6s
    font-size: 100vw * 23 / 375
    margin: 0.78em 0 1.52em

  .s6p
    font-size:  100vw * 16 / 375
    line-height: 1.7

// --------------------------------
// MOON
.moon
  position: absolute

@media screen and (min-width: $bp-pc)
  .moon
    left: 0
    bottom: -2vw
    width: 7vw
@media screen and (max-width: $bp-mb)
  .moon
    right: 0
    top: -10vw
    width: 17vw

// --------------------------------
// tree
.s6tree
  position: absolute
  z-index: 3
  right: 0
  img
    width: 100%

@media screen and (min-width: $bp-pc)
  .s6tree
    width: 27vw
    bottom: 5.1vw
@media screen and (max-width: $bp-mb)
  .s6tree
    width: 47vw
    top: 88vw

// --------------------------------
// HR
#sec6-2
  padding: 3vw 6vw
  display: flex
  justify-content: center
.s6hr
  position: relative
  width: 80vw
  @include liinCircle
  b
    width: 5px
    height: 5px
    position: absolute
    border-radius: 50%
    right: 0
    top: 0
  &:before, &:after, b
    background: #000
  &:before
    left: 0
    top: 0
  &:after
    top: 2px
    left: 0
    right: 0
    height: 1px

@media screen and (max-width: $bp-mb)
  .s6hr
    width: 100%
</style>
