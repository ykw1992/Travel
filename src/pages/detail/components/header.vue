<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
        景点详情
      </router-link>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
  @import "~style/varibles.styl"
  .header-abs
    position: absolute
    top .2rem
    left .2rem
    width .8rem
    height .8rem
    line-height .8rem
    border-radius .4rem
    text-align center
    background-color: rgba(0,0,0,.8);
    .header-abs-back
      color #fff
      font-size .4rem
  .header-fixed
    z-index: 2
    position:fixed
    top 0
    left 0
    right 0
    height .86rem
    line-height $headerHeight
    color #fff
    text-align center
    background $bgColor
    font-size .32rem
    .header-fixed-back
      position absolute
      text-align: center
      font-size: .4rem
      width .64rem
      top 0
      left 0
      color #fff
</style>
