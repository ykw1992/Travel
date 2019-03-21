<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="请输入城市名或拼音">
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import "~style/varibles"
  .search
    line-height .72rem
    background-color: $bgColor
    padding 0 .1rem .1rem .1rem
    .search-input
      box-sizing border-box
      height .62rem
      line-height .62rem
      text-align center
      border-radius .06rem
      width 100%
      color #666
      padding 0 .1rem
</style>
