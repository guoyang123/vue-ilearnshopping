<template>
    <div class="container" @click="clickExitGallary">
      <div class="wrapper">
        <swiper :options="swiperOption" >
          <!-- slides -->
          <swiper-slide v-for="(item,index) of gallaryBanners" :key="index">
            <img class="swiper-img" :src="galleryObj.imageHost+item"/>
          </swiper-slide>
          <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>
    export default {
        name: "CommonGallary",
        props:{
          galleryObj:Object,

        },
        computed:{
          gallaryBanners:function () {
            return (this.galleryObj.subImages || "").split(",");
          }
        },
        data(){
          return {
            swiperOption:{
               pagination:'.swiper-pagination',
               paginationType:"fraction",
               observeParents: true,
               observer:true
            }
          }
        },
      methods:{
        clickExitGallary(){
          this.$emit("close")
        }
      }
    }
</script>

<style scoped lang="stylus">

   .wrapper >>> .swiper-container
     overflow :inherit
   .container
     position :fixed
     display :flex
     flex-direction :column
     justify-content :center
     top:0
     left :0
     right :0
     bottom:0
     background:#000000
     z-index:99
     .wrapper
       /*overflow :hidden*/
       height :0
       width: 100%
       padding-bottom :100%
       .swiper-img
         width :100%
       .swiper-pagination
         color: #ffffff
         bottom: -1rem
</style>
