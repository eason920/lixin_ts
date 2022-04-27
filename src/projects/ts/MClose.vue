<template>
  <div>
    <div id="lbMasker" v-if="bIsOpen" @click="toggleSidebar">
      <ul>
        <li
          data-aos="fade-up"
          :data-aos-delay="150 * i"
          :key="item.name"
          v-scroll-to="{
            element: `#${item.section}`,
            offset: item.mobileOffset
          }"
          v-for="(item, i) in list"
        >
          <a href="#" @click.prevent="">{{ item.name }}</a>
        </li>
      </ul>
    </div>
    <div id="lbswitch" :class="[{ open: bIsOpen }]" @click="bIsOpen = !bIsOpen">
      <div class="lbswitch-wrapper">
        <div class="lbswitch-line is-tb"></div>
        <div class="lbswitch-line is-m"></div>
        <div class="lbswitch-line is-m2"></div>
        <div class="lbswitch-line is-tb"></div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'
import navList from '@/info/navList'

export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      isTablet,
      list: navList,
      bIsOpen: false
    }
  },

  methods: {
    toggleSidebar() {
      console.log('got fnb')
      this.bIsOpen = !this.bIsOpen
    }
  },

  created() {},

  mounted() {},

  computed: {
    offset() {
      if (this.isMobile) {
        return -39
      }

      if (this.isTablet) {
        return -45
      }

      return -56
    }
  }
}
</script>

<style lang="sass">
//#a11b00
$deepo: rgb(161, 27, 0, .7)
body.fixed
  overflow: hidden
</style>

<style lang="sass" scoped>
#lbMasker
  position: fixed
  top: 0
  right: 0
  bottom: 0
  left: 0
  margin: auto
  z-index: 99
  animation: start 1s linear forwards
  background-color: rgb(161, 27, 0, .85)
  ul
    padding-top: 12vh
    position: relative
    z-index: 1
  a
    text-decoration: none
    padding: 3vh 0
    display: block
    color: #fff
    font:
      size: 26px
      weight: 600

@keyframes start
  0%
    opacity: 0
  100%
    opacity: 1
//-------------
#lbswitch
  top: 0
  right: 0
  left: auto
  z-index: 99
  position: fixed
  width: 45px
  height: 45px
  cursor: pointer
  background-color: rgb(161, 27, 0, .7)
  transition: .3s

.lbswitch-wrapper
  position: absolute
  top: 0
  bottom: 0
  right: 0
  left: 0
  display: flex
  justify-content: space-between
  margin: auto
  width: 26px
  height: 26px
  flex-direction: column

.lbswitch-line
  position: relative
  margin: auto
  width: 100%
  height: 1px
  background: rgba(255,255,255, 1)
  //
  transform: scaleX(1)
  opacity: 1
  transition: 1s
  &.is-m2
    // opacity: 0
    position: absolute
    transform-origin: 50% 50%
    top: calc(50% - 1px)

.open
  &#lbswitch
    background-color: rgb(161, 27, 0, 0)
  .is-tb
    transform: scaleX(2)
    opacity: 0
  .is-m
    transform: rotate(45deg)
    background-color: #fff
  .is-m2
    transform: rotate(-45deg)
    background-color: #fff
</style>
