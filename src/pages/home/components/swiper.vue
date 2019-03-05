<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <!-- slides -->
      <swiper-slide v-for="item of imgList" :key="item.id"><img class="swiper-img" :src="item.imgUrl" alt=""></swiper-slide>
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
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      imgList: [
        {id: '0001', imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/fc/fc75b872467d8e79a3.water.jpg_710x360_04d6be48.jpg'},
        {id: '0002', imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/fc/fc75b872467d8e79a3.water.jpg_710x360_04d6be48.jpg'},
        {id: '0003', imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/c7/c7715b0945b2cfeba3.water.jpg_710x360_54b315df.jpg'}]
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
      padding-bottom 50.7%
    .swiper-img
     width : 100%
     height : 100%
</style>
