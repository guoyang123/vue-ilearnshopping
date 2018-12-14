<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <div>test</div>
   <!-- <div class="home">home</div>
   <router-link to="/list">列表页</router-link>-->

  </div>
</template>

<script>
  import HomeHeader from "./components/Header"
  import HomeSwiper from './components/Swiper'
    export default {
        name: "home",
        components:{
          HomeHeader,HomeSwiper
      }
    }
</script>

<style scoped>


</style>
