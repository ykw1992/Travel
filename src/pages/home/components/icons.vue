<template>
  <div class="icons" >
    <swiper :options="swiperOption" >
      <swiper-slide v-for="(page ,index) of pages" :key="index">
      <div class="icon" v-for="item of page" :key="item.id">
        <div class="icon-img-contain">
          <img   class='icon-img' :src="item.url"  alt="">
        </div>
        <p class="icon-desc">{{item.des}}</p>
      </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data: function () {
    return {
      swiperOption: {},
      imgList: [
        {id: '0001', url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', des: '热门景点'},
        {id: '0002', url: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png', des: '一日游'},
        {id: '0003', url: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png', des: '上海必游'},
        {id: '0004', url: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png', des: '动植物园'},
        {id: '0005', url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20192/23e0e0f2e3ab69f6644e5625b31c35a1.png', des: '女神节特惠'},
        {id: '0006', url: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png', des: '踏青赏花'},
        {id: '0007', url: 'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png', des: '东方明珠'},
        {id: '0008', url: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png', des: '野生动物园'},
        {id: '0009', url: 'http://img1.qunarzz.com/piao/fusion/1803/de/f26be47a6bf02a02.png', des: '上海迪士尼'},
        {id: '0010', url: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png', des: '城市风光'}]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.imgList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~style/varibles.styl"
  @import "~style/mixins.styl"
  .icons >>> .swiper-container
    overflow: hidden
    height : 0
    padding-bottom : 50%
    .icon
      float left
      overflow : hidden
      position : relative
      height : 0
      width : 25%
      padding-bottom : 25%
      .icon-img-contain
        position : absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing :border-box
        padding .1rem
        .icon-img
          display : block
          margin 0 auto
          height 100%
      .icon-desc
        position: absolute;
        bottom 0
        left 0
        right 0
        line-height .44rem
        height .44rem
        text-align center
        color $darkTextColor
        ellipsis()
</style>
