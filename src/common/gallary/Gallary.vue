<template>
  <div class="container" @click="handleGalaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <!-- slides -->
        <swiper-slide v-for="(item, index) in imgs" :key="index">
          <img class="swiper-img"
               :src="item" >
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
        <!--<div class="swiper-button-prev" slot="button-prev"></div>-->
        <!--<div class="swiper-button-next" slot="button-next"></div>-->
        <!--<div class="swiper-scrollbar"   slot="scrollbar"></div>-->
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CommonGallary',
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGalaryClick () {
      this.$emit('close')
    }

  },
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: inherit
  .container
    display: flex
    flex-direction column
    justify-content center
    z-index 99
    position fixed
    left:0
    right 0
    top:0
    bottom:0
    background #000
    .wrapper
      height 0
      width 100%
      padding-bottom 66.6%
      .swiper-img
        width 100%
      .swiper-pagination
        color #fff
        bottom -1rem
</style>
