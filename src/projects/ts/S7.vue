<template>
  <div class="relative sec7-outer">
    <section id="sec7">
      <img src="./7/exterior.png" alt="外觀" class="bg" v-if="!isMobile" loading="lazy">
      <img src="./7/exterior_m.png" alt="外觀" class="bg" v-if="isMobile" loading="lazy">
      <div class="s7box1">
        <div class="s7b1l">
          <div
            class="s7t"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false"
          >
            鋼柱結構 制震地標
          </div>
          <div
            class="s7s"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false"
          >
            結構同步101 超越SRC
          </div>
          <div
            class="s7p"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false"
          >
            採用101、宏盛帝寶等級C.F.T.鋼柱，採高雄中鋼高拉力鋼板，柱內由下往上以高壓灌漿混凝土入鋼柱；超越宏盛帝寶7000磅高強度混凝土。
          </div>
          <ul class="s7u">
            <li
              data-aos="zoom-in"
              data-aos-duration="800"
              data-aos-once="false"
            >
              高強度耐火性能
            </li>
            <li
              data-aos="zoom-in"
              data-aos-duration="800"
              data-aos-once="false"
            >
              剛度提高，地震與風吹下比傳統SRC不易變形
            </li>
            <li
              data-aos="zoom-in"
              data-aos-duration="800"
              data-aos-once="false"
            >
              提高混凝土強度，柱截面變小，室內空間增大
            </li>
            <li
              data-aos="zoom-in"
              data-aos-duration="800"
              data-aos-once="false"
            >
              具有穩定的滯回性能，抗震性能大幅提高
            </li>
          </ul>
        </div>
        <div class="s7b1r">
          <img
            src="./7/src.png"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false" loading="lazy"
          />
          <img
            v-if="!isMobile"
            src="./7/cft.png"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false" loading="lazy"
          />
          <img
            v-else
            src="./7/cft_m.png"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false" loading="lazy"
          />
        </div>
      </div>
      <div class="s7box2">
        <div
          class="s7tree"
          data-aos-once="false"
          data-aos="fade"
          data-aos-duration="800"
          data-aos-delay="0"
        >
          <img src="./all/tree1.png" class="treeAni" v-if="!isMobile" />
        <img src="./all/tree1_m.png" class="treeAni" loading="lazy" v-else />
        </div>
        <div data-aos="zoom-in" data-aos-duration="800" data-aos-once="false">
          <img v-if="!isMobile" src="./7/img2.png" loading="lazy" />
          <img v-else src="./7/img2m.png" loading="lazy" />
        </div>
      </div>
      <div class="s7box3">
        <div class="s7b3t">
          <span data-aos="zoom-in" data-aos-duration="800" data-aos-once="false"
            >494組制震系統 制震超越6級</span
          >
          <p data-aos="zoom-in" data-aos-duration="800" data-aos-once="false">
            發生4級以上地震，大樓會呈現8字型的搖擺，本案採用日本進口特殊鋼材制震器，非傳統油壓式制震，避免將來漏油的風險，總樓高25樓，最高裝至22樓，充份地發揮鋼構件的優異韌性來吸收地震能量。最高規格的安全守護，打造建築地標。
          </p>
        </div>
        <img src="./all/logobg.png" class="s7b3b1"
          data-aos-once="false"
          data-aos="fade-up"
          data-aos-duration="2500"
          data-aos-delay="200" />
        <img
          src="./all/bird2.png"
          class="s7b3b2"
          data-aos-once="false"
          data-aos="fade-right"
          data-aos-duration="2500"
          data-aos-delay="200"
        />
        <!-- <div class="s7b3b">
          <img
            src="./7/img3.jpg"
            data-aos="zoom-in"
            data-aos-duration="800"
            data-aos-once="false"
          />
        </div>  -->
      </div>
      <div class="wave">
        <svg
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 3813 217"
          style="enable-background:new 0 0 3813 217;;transform-origin: 50% 100%"
          xml:space="preserve"
        >
          <path
            class="waveOrange"
            d="M3813,85c-406.1,5.2-421,162-1056.2,67.7c-264.8-34.4-520.5-88.9-829-128.4C1525-27.4,1484.1,18.6,1400,42.8c-84,24.2-232.3,79.5-557,83.2C576,129,311,81,0,85v132h3813V85z"
          />
        </svg>
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
// start
.s7t
  @include liinCircle
  width: 100%
  position: relative
  &:before, &:after
    background: #000
  &:before
    right: 0
    top: 5px
  &:after
    height: 1px
    top: 7px
    right: 0
    left: 150px

.s7b1l
  display: flex
  align-items: flex-start
  text-align: justify
  flex-direction: column
.s7s
  font:
    size: 2vw
    weight: 700
  padding: 1.5vw 0 2.5vw

@media screen and (min-width: $bp-pc)
  .s7b1l
    width: 23vw

  .s7t
    font-size:  100vw * 15 / 1920

  .s7p
    font-size: 100vw * 18 / 1920
    line-height: 1.7
@media screen and (max-width: $bp-mb)
  .s7b1l

  .s7t
    font-size:  100vw * 15 / 375

  .s7s
    font:
      size: 7.5vw
      weight: 700
    padding: 5vw 0 10vw

  .s7p
    font-size: 100vw * 15 / 375
    line-height: 1.7

// --------------------------------
// BOX1
.s7u
  padding:
    top: 2vw
    left: 20px
  li
    font-size: 100vw * 18 / 1920
    line-height: 1.3
    padding-bottom: 1.1em
    position: relative
    &:before
      width: 0.5em
      height: 0.5em
      position: absolute
      background: #000
      border-radius: 50%
      content: ''
      left: -0.94em
      top: 0.38em

@media screen and (max-width: $bp-mb)
  .s7u
    width:110%
    padding:
      top: 10vw
      bottom: 7vw
    li
      font-size: 100vw * 13 / 375

@media screen and (min-width: $bp-pc)
  .s7box1
    padding: 0 5vw
    display: flex
    justify-content: space-between
  .s7b1l
    width: 35vw
  .s7b1r
    width: 43vw
    display: flex
    align-items: flex-start
    justify-content: space-between
    img
      &:nth-child(1)
        width: 37%
      &:nth-child(2)
        width: 56%

@media screen and (max-width: $bp-mb)
  .s7box1
    padding: 10vw 8vw
  .s7b1l

  .s7b1r
    display: flex
    align-items: flex-start
    justify-content: space-between
    img
      &:nth-child(1)
        width: 42%
      &:nth-child(2)
        width: 51%

// --------------------------------
// BOX2
.s7box2
  position: relative

@media screen and (min-width: $bp-pc)
  .s7box2
    padding-right: 5vw
    display: flex
    justify-content: flex-end
    img
      width: 50vw
@media screen and (max-width: $bp-mb)
  .s7box2
    padding: 0 8vw 40vw
    img
      width: 100%

// --------------------------------
// tree
.s7tree
  position: absolute
  z-index: 3
  img
    width: 100%

.treeAni2

@media screen and (min-width: $bp-pc)
  .s7tree
    width: 29vw
    bottom: 0vh
    left: 0
    transform: translateX(-10%)
    img
      transform: rotateY(180deg) skewY(-2deg) translateX(-100%)
      animation: tree2 5s infinite alternate
      transform-origin: 0 50%

  @keyframes tree2
    to
      transform: rotateY(180deg) skewY(0) translateX(-100%)

@media screen and (max-width: $bp-mb)
  .s7tree
    right: 0
    width: 60vw
    bottom: 2vh
    transform: translateX(10%)

// --------------------------------
// BOX3
@media screen and (min-width: $bp-pc)
  .s7box3
    padding: 10vw 5vw 0

  .s7b3t
    text-align: left
    span
      font:
        size: 1.9vw
        weight: 700
    p
      width: 30vw
      padding:
        top: 1.5vw
        bottom: 5vw
      font-size: 18px
      line-height: 1.6

  .s7b3b
    text-align: left
    img
      width: 24vw
      border-radius: 12vw
  .s7b3b1
    width: 25vw
    margin: 3vw 0 3vw -40vw

  .s7b3b2
    width: 15vw
    margin: 0 0 17vw -31vw

@media screen and (max-width: $bp-mb)
  .s7box3
    padding: 0 8vw 0

  .s7b3t
    text-align: left
    span
      font:
        size: 6vw
        weight: 700
    p
      padding:
        top: 10vw
        bottom: 12vw
      font-size: 16px
      line-height: 1.6

  .s7b3b
    text-align: left
    img
      width: 42vw
      border-radius: 21vw

  .s7b3b1
    width: 42vw
    margin: 5vw 0 -1vw -40vw
  .s7b3b2
    width: 30vw
    margin: 0vw 0 24vw -50vw

// --------------------------------
// outer
.sec7-outer
  background:
    image: url(./all/bgw.jpg)
#sec7
  position: relative
  background:
    image: url(./all/mount.png)
    size: 110%
    position: 50% 125%
    repeat: no-repeat
  padding:
    top: 5vw
    bottom: 14vh
.bg
  position: absolute
  bottom: -1vw
  right: 11vw
  width: 580 * 100vw / 1920
  z-index: 3

@media screen and (max-width: $bp-mb)
  #sec7
    background:
      size: 110% auto
      position: 100% 103%
      repeat: no-repeat
    padding-bottom: 10vh
  .bg
    position: absolute
    bottom: 0vw
    right: 5.5vw
    width: 145 * 100vw / 375

// --------------------------------
// wave
.wave
  bottom: -1px
  svg
    // animation: none
    // transform: translate(-5%, 20%)

@media screen and (max-width: $bp-mb)
  .wave
    svg
      // transform: translate(-5%, 8%)
</style>
