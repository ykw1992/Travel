<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市\景点\游玩主题</div>
    <div class="header-right">城市<span class="iconfont">&#xeb6d;</span></div>
  </div>
</template>

<script>
export default {
  name: 'Homeheader'
}
</script>
<!--scoped 表示样式只对当前的组件有效-->
<!--1rem =html font-size =50px-->
<style lang="stylus" scoped>
  @import '~style/varibles.styl'
  .header
    display: flex
    background-color: $bgColor
    color #fff
    line-height: .86rem
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-size: .4rem
    .header-input
      flex: 1
      background-color: #fff
      color :#ccc
      border-radius :.1rem
      margin-top :.12rem
      margin-left .2rem
      height :.64rem
      line-height:.64rem
    .header-right
      width: 1.24rem
      float: right
      text-align : center

</style>
