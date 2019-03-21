<template>
  <div class="list">
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
    <div class="item">A</div>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet'
}
</script>

<style lang="stylus" scoped>
  @import "~style/varibles"
  .list
    position absolute
    top 1.58rem
    right 0
    bottom 0
    width .4rem
    background-color: red
    display flex
    flex-direction column
    justify-content center
      .item
        font-size .44rem
        color $bgColor
        text-align center
</style>
