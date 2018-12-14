<template>
  <div class="wrapper">


  <swiper :options="swiperOption" >
    <!-- slides -->
    <swiper-slide v-for="(item,index) of swiperList" :key="index ">
      <img class="swiper-img" :src="item.imgUrl"/>
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
    export default {
        name: "HomeSwiper",
        data (){
          return {
            swiperOption:{
              pagination:'.swiper-pagination',
              loop:true
            },
            swiperList:[{
              id:'001',
              imgUrl:'http://piwbqm1dn.bkt.clouddn.com/topbanner.png'
            },{
              id:'002',
              imgUrl:'http://piwbqm1dn.bkt.clouddn.com/combanner.png'
            },{
              id:'003',
              imgUrl:'http://piwbqm1dn.bkt.clouddn.com/topbanner.png'
            }

            ]
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
