<template>
  <div>
    <div class="search">
      <input type="text" class="search-input" placeholder="请输入城市名或拼音" v-model="keyword">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom"
            v-for="item of list"
            :key="item.id"
            >{{item.name}}
        </li>
        <li class="search-item border-bottom" v-show="hsaNoData">
          没有找到匹配数据
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              return result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  computed: {
    hsaNoData () {
      return !this.list.length
    }
  },
  props: {
    cities: Object
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
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
  .search-content
    z-index 1
    overflow hidden
    background #eee
    position absolute
    top:1.58rem
    left 0
    right 0
    bottom 0
    .search-item
      line-height .62rem
      color #666
      padding-left .2rem
      background #fff
</style>
