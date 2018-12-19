<template>
  <div class="wrapper">


  <swiper :options="swiperOption" >
    <!-- slides -->
    <swiper-slide  v-for="(item,index) of banners" :key="index " v-if="index<4" data-swiper-autoplay="2000">
      <router-link tag='img' :to="'/detail/'+item.id" class="swiper-img" :src="item.imageHost+item.mainImage"/>
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
    export default {
        name: "HomeSwiper",
        props:{
          banners:Array
        },
        data (){
          return {
            swiperOption:{
              pagination:'.swiper-pagination',
              loop:true,
              autoplay: 1000
            }
          }
        }
    }
</script>

<style scoped lang="stylus">
  .wrapper >>> .swiper-pagination-bullet-active
    background :#ffffff
  .wrapper
    /*设置图片宽高自适应*/
    overflow :hidden
    width :100%
    height :0
    padding-bottom :26%
    background :#eee
    .swiper-img
      width :100%

</style>
