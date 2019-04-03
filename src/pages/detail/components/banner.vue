<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg">
      <div class="banner-info">
        <div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe60e;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGalary" @close="handleGalaryClose"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGalary: false,
      imgs: [
        'http://img1.qunarzz.com/sight/p0/1709/c5/c5685639103c66ea3.img.png_r_800x800_e4a29d19.png',
        'http://img1.qunarzz.com/sight/p0/1509/11/11f48afdd282f695.img.jpg_r_800x800_979033db.jpg'
      ]
    }
  },
  methods: {
    handleBannerClick () {
      this.showGalary = true
    },
    handleGalaryClose () {
      this.showGalary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow: hidden
    height:0
    padding-bottom: 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      bottom:0
      left 0
      right 0
      color #fff
      line-height .6rem
      background-image linear-gradient(top , rgba(0,0,0,0), rgba(0,0,0,0.8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .banner-number
        height .32rem
        line-height .32rem
        margin-top .14rem
        padding: 0 .4rem
        border-radius 0.2rem
        font-size .24rem
        background rgba(0,0,0,.8)
        .banner-icon
          font-size .24rem
</style>
