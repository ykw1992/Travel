<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont back-city">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import "~style/varibles"
  .header
    position relative
    height .86rem
    line-height $headerHeight
    overflow hidden
    color #fff
    text-align center
    background $bgColor
    font-size .32rem
    .back-city
      position absolute
      text-align: center
      font-size: .4rem
      width .64rem
      top 0
      left 0
      color #fff
</style>
