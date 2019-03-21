<template>
  <div class="list">
    <div class="item" v-for="(item ,key ) of cities" :key="key">{{key}}</div>
  </div>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
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
    display flex
    flex-direction column
    justify-content center
    .item
      color $bgColor
      text-align center
      line-height .34rem
</style>
