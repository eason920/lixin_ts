<template>
  <div class="relative">
    <section id="sec3">
      <div class="s3box">
        <div class="s3pic">
          <!-- <img src="./3/bg.jpg" class="basic" />
          <img src="./3/bgt.png" class="float" /> -->
          <!-- isMobile -->
          <!-- <img src="./3/bgtm.png" class="float"/> -->
        </div>
      </div>
      <img
        class="finger"
        src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFIAAABJCAYAAACuPXHDAAAACXBIWXMAABYlAAAWJQFJUiTwAAAErElEQVR4nO2cv3LTQBDGvzCpGGbkki4u6G2eIE5FGfMEVloazBMQnoA00OI8AaGkQn4ClCdAfgLkGUpmjrnMKuxsJFmK7p9kfzOa2JYs636629vdW+VIKYUWiunQVZsv9VCt23ncEuIXep0BSAYKccbaicYwdY9ssMXqv1YNv9PnbcXaGzdpxwFi9dYK5gGiIZi+Ic6UUkvapn2G6QviXCmVqYfKCG7vYPqAGJcAlJr3DaZriOMSaIlSKhWf5UqpUZ9guoSotysBi9vFmYC5DBBkJczCIX8D4BO9/k5O6KyjY1vmsE/Z60sAqTj+GsCC3uvfv6o4x6jjtXWRZvMcwCty3J8C+FxQlkPLhMruZsLOWzap8FGRNDhHCEp5j/xNf/8CuAXwx9PdzhockzY4xraeAZhQiH3HrgD5moaW3vmChlUIF1ympeffnxKrY+p0mh2e0M6c4OkdER04rT/fXqqAGBGrGbG7B3mAuVuVECFA4gCzUrUQUQISB5gPtBMiKkDiAPNejSCiBiQOMJtDxA6Q2GOYrSCiAUjsIczWENFi8auAWcTPTSKQvipj7WsEsQ1IDhNNT95TPaqdbUAOHSBX63a2BelSp9SglK2j34R6M5tMNj4VEdAF5f4yymMGp9BBSmmw70MsmQkZpHY9zgBcUOZ8y/bpHqrYltGwj2vOZ1Uhg8zJLq4I0JjglukEwDkb/nPXFxvyZCOVE6BfO47TUL8CeMeS05lt37dPIEEwNgQLNPQzikbmbOFM62PJ97+RCTBuY/s22aCkZ3H7+FLYUqli+KdkKoypjyDrlIretq0AO6FjjS3rDg0kqHcWKmAd0SLVmu2LKtbNHyXTIMcUp84CzBDd0HV9YJ8tTPVKUyBH5KroGfUHbT/Jfnnz7Sp0KYa7kRtuAqSGmFEoJ3VCxj3xXGYiZXzN3gRIbWci9n5T4jifCts1OHX1I0fCd7tmQ3lMM2jRU8t6rFRCE0OduhZ3WVHXHsnty1bYw4wafR1IW63KZGRTlSeMCfjEUZty5uY4q1/qCpJHGSdiXYdrSTO5C6U+hn/XoZ0JJ/emwp1IKM4drEzM2jxjXbdcO+jnF02A1OAu2PuIoEm/cajPLt7JVGSzovxfoUmJE57vyMy4VBNXrJVMxtpXwtWZlAznIoFwFFAPNbIqaTppEQuY5yYzLIYkTY4RF8lGGi0WM/lbH2soNbKSlbKVj5xTzF1oZToj3UH8OtamTmoLZC56YRSQ+8NBGqvasJkhT8VMfhrAox0QUY+xELLtPwd5jBLmbmzJRvksC8xZ2u/MlPfgYs0mZv5j5Ll2Zyxyp8ZuqAuQmXCBFh7Xc/iw3vQNJKgXbsR7H+IgjQYELpdjObxzT+7QIECuPPfKKSt1QZ9BQthK19EOXwa5Ne05uAbJnfLIMUz+W70vospFptwVyLkY1saXhn3U/vBGuARZaG0jIPANMnLkU1od1vAEMheVGLZBzkQ0Y6Xiw1dZH08WuABZaG3rOR1fILmNcgnS2vKGL5C8Qbar1PiNGhxILpulLDLbY62EJQQbaVM8nt/YfI7R1+MhskHWs8u2k8lDLMavktWnavcJpD1zAuAfMiguMm+CB/8AAAAASUVORK5CYII="
        lazy="loaded"
      />
    </section>
  </div>
</template>

<style lang="sass">
@import "src/assets/style/myvar"
#sec3
  // height: 100vh

.finger
  position: absolute
  top: 7.8125vw
  width: 4.2708333333vw
  animation: move 2s ease-in-out infinite alternate-reverse

@keyframes move
  0%
    transform: translateX(0)
  to
    transform: translateX(-50%)

.s3box

$area: 300px
.s3pic
  background:
    image: url(./3/bg.jpg)
    size: contain
    position: 0 100%
    repeat: no-repeat
    color: #0059a9
  font-size: 0
  position: relative
  // height: 42vw
  width: calc( 100vw + #{$area})
  transform: translateX( calc( #{$area} / 2 * -1 ) )
  &:after
    content: ""
    position: absolute
    width: 100%
    height: 100%
    left: 0
    top: 0
    background:
      image: url(./3/bgt.png)
      size: contain

// @media screen and (min-width: $bp-pc)
@media screen and (max-width: $bp-mb)
  .s3pic
    background:
      image: url(./3/bg.jpg)
      size: 120% auto
      position: 0 100%
    &:after
      background:
        image: url(./3/bgtm.png)
        size: 76% auto
        position: -10% 60%
        repeat: no-repeat
</style>

<script>
import $ from 'jquery'
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'

export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      isTablet
    }
  },

  methods: {
    fnMLeft() {}
  },

  created() {},

  mounted() {
    if (!isMobile) {
      console.log('=========PC=========')
      const ww = ($(window).width() + 300) * 0.5625
      console.log('ww', ww)
      $('.s3pic').css('height', ww)
      let mStart = 0
      $('.s3box').mousedown(e => {
        if (event.which === 1) {
          if (mStart === 0) {
            mStart = e.pageX
          }
          $('.s3box').addClass('move')
          console.log('ok')
        }
      })
      $('.s3box').mouseup(event => {
        $('.s3box').removeClass('move')
        console.log('up')
      })

      $('#sec3').on('mousemove', '.s3box.move', e => {
        let move = mStart - e.pageX
        switch (true) {
          case move <= -150:
            move = -150
            break
          case move >= 150:
            move = 150
            break
          default:
        }
        const trans = 'translateX(calc(-150px + ' + move + 'px))'
        console.log(move, trans)
        // console.log('e.pageX', e.pageX)
        $('.s3pic').css('transform', trans)
      })
    } else {
      console.log('=========MB=========')
      const ww = ($(window).width() + 300) * 0.611
      console.log('ww', ww)
      $('.s3pic').css('height', ww)
      // -----------------------
      // touchstart', 'touchend
      let startX = 0
      $('.s3box').on('touchstart', e => {
        if (startX === 0) {
          startX = e.targetTouches[0].pageX
        }
        console.log('touchstart', startX)
        // $('.s3box').addClass('move')
      })

      $('.s3box').on('touchend', e => {
        // console.log('touchend', e.targetTouches[0].pageX)
        // $('.s3box').removeClass('move')
      })

      $('.s3box').on('touchmove', e => {
        let move = (e.targetTouches[0].pageX - startX) * -1
        switch (true) {
          case move <= -150:
            move = -150
            break
          case move >= 150:
            move = 150
            break
          default:
        }
        const trans = 'translateX(calc(-150px + ' + move + 'px))'
        console.log(move, trans)
        // // console.log('e.pageX', e.pageX)
        $('.s3pic').css('transform', trans)
      })
    }
  },

  computed: {}
}
</script>
