<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <new-product></new-product>
   <!-- <div class="home">home</div>
   <router-link to="/list">列表页</router-link>-->

  </div>
</template>

<script>
  import HomeHeader from "./components/Header"
  import HomeSwiper from './components/Swiper'
  import HomeIcons from './components/Icons'
  import HomeRecommend from './components/Recommend'
  import NewProduct from './components/NewProduct'
    export default {
        name: "home",
        components:{
          HomeHeader,HomeSwiper,HomeIcons,HomeRecommend,NewProduct
      }
    }
</script>

<style scoped>


</style>
