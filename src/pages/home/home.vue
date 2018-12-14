<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <div>test</div>
   <!-- <div class="home">home</div>
   <router-link to="/list">列表页</router-link>-->

  </div>
</template>

<script>
  import HomeHeader from "./components/Header"
  import HomeSwiper from './components/Swiper'
  import HomeIcons from './components/Icons'
    export default {
        name: "home",
        components:{
          HomeHeader,HomeSwiper,HomeIcons
      }
    }
</script>

<style scoped>


</style>
