<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icon></home-icon>
  </div>
</template>
<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeIcon from './components/icons'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcon
  }
}
</script>

<style>

</style>
