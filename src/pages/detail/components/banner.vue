<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe60e;</span>
          {{this.gallaryImgs.length}}
        </div>
      </div>
    </div>
    <common-fade>
      <common-gallary :imgs="gallaryImgs" v-show="showGalary" @close="handleGalaryClose"></common-gallary>
    </common-fade>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import CommonFade from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      showGalary: false
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
    CommonGallary,
    CommonFade
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
