<template>
  <div class="home no-padding-top">
    <Loading :loading="load" />
    <SideNavigation v-if="isSide" />
    <Navigation v-if="!isMobile" />
    <MClose v-else />
    <vue-lazy-component class="section" id="section1" @init="init">
      <S1 />
    </vue-lazy-component>
    <!--
    <vue-lazy-component class="section" id="section2" @init="init">
      <S2 />
    </vue-lazy-component>  -->
    <vue-lazy-component class="section" id="section3" @init="init">
      <S3 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section4" @init="init">
      <S4 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section5" @init="init">
      <S5 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section6" @init="init">
      <S6 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section7" @init="init">
      <S7 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section8" @init="init">
      <S8 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section9" @init="init">
      <S9 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="section10" @init="init">
      <S10 />
    </vue-lazy-component>
    <vue-lazy-component class="section" id="contact">
      <ContactSection />
    </vue-lazy-component>
    <!-- ======================== -->
    <MobileNav />
  </div>
</template>

<script>
import $ from 'jquery'
import Navigation from '@/layouts/Navigation.vue'
import { isMobile } from '@/utils'
import SideNavigation from '@/layouts/SideNavigation.vue'
import ContactSection from '@/layouts/ContactSection.vue'
import MobileNav from '@/layouts/MobileNav.vue'
import MClose from '@/projects/ts/MClose.vue'
import Loading from '@/components/Loading.vue'
import S1 from '@/projects/ts/S1.vue'
// import S2 from '@/projects/ts/S2.vue'
import S3 from '@/projects/ts/S3.vue'
import S4 from '@/projects/ts/S4.vue'
import S5 from '@/projects/ts/S5.vue'
import S6 from '@/projects/ts/S6.vue'
import S7 from '@/projects/ts/S7.vue'
import S8 from '@/projects/ts/S8.vue'
import S9 from '@/projects/ts/S9.vue'
import S10 from '@/projects/ts/S10.vue'

export default {
  name: 'home',
  components: {
    Loading,
    Navigation,
    SideNavigation,
    ContactSection,
    MobileNav,
    MClose,
    S1,
    // S2,
    S3,
    S4,
    S5,
    S6,
    S7,
    S8,
    S9,
    S10
  },

  data() {
    return {
      isMobile,
      isSide: false,
      load: true
    }
  },
  created() {
    $(document).ready(() => {
      // Images loaded is zero because we're going to process a new set of images.
      var imagesLoaded = 0
      // Total images is still the total number of <img> elements on the page.
      var totalImages = $('img').length

      console.log('totalImages', totalImages)

      const allImagesLoaded = () => {
        this.load = false
        $('.s1Masker').addClass('start')
      }
      const imageLoaded = () => {
        imagesLoaded++
        if (imagesLoaded === totalImages) {
          allImagesLoaded()
        }
      }
      $('img').each(function(idx, img) {
        $('<img>')
          .on('load', imageLoaded)
          .attr('src', $(img).attr('src'))
      })
    })
  },
  mounted() {},
  methods: {
    init() {}
  }
}
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css?family=Noto+Serif+TC')
@import "src/assets/style/myvar"
@import @/assets/style/wave
*
  font-family: "Noto Serif TC", serif !important
  letter-spacing: 1px
  // Noto Sans CJK TC  粗細Regular 400
  // Noto Serif CJK TC  粗細Regular 400  Bold 700

// --------------------------------
// TREE
.treeAni
  animation: tree 5s infinite alternate
  transform: skewY(-2deg)
  transform-origin: 100% 50%
@keyframes tree
  to
    transform: skewY(0)
*
  letter-spacing: 2px

// --------------------------------
// SWIP-DOT
// --------------------------------
// SECTION
section
  user-select: none
//   overflow: hidden
//   position: relative
//-- ----------------------------
// AOS
.transorileft
  transform-origin: 0 50%

.transorileftTop
  transform-origin: 0
</style>

<style lang="scss">
// @import url('https://fonts.googleapis.com/css?family=Playball&display=swap');
// @import '../assets/style/variableColor.scss';

// .section,
// .section .fp-slide,
// .section .fp-tableCell {
//   height: auto !important;
// }
</style>
