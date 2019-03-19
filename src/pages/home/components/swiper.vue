<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwipper">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id"><img class="swiper-img" :src="item.imgUrl" alt=""></swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
      <!--<div class="swiper-button-prev" slot="button-prev"></div>-->
      <!--<div class="swiper-button-next" slot="button-next"></div>-->
      <!--<div class="swiper-scrollbar"   slot="scrollbar"></div>-->
    </swiper>
  </div>
</template>

<script>

export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwipper () {
      return this.list.length
    }

  }
}

</script>

<style lang="stylus" scoped>
  /*scoped属性导致 swiper插件中的class=swiper-pagination-bullet-active修改后无法影响到swiper
    但是可以通过该组件的class=wrapper，穿透>>>插件中的class来完成修改
  */
    .wrapper >>>.swiper-pagination-bullet-active
      background: #fff !important
    .wrapper
      overflow hidden
      width 100%
      height 0
      padding-bottom 31.2%
    .swiper-img
     width : 100%
     height : 100%
</style>
