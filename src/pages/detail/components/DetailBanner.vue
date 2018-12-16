<template>
  <div>
    <div class="banner" @click="handleClickBanner">
      <img class="banner-img" :src="detailheader.imageHost+detailheader.mainImage" >
      <div class="banner-info">
        <p class="banner-title"></p><!--{{detailheader.name}}-->
        <p class="banner-number"><span class="iconfont icon-text">&#xe61a;</span>{{gallaryBanners.length}}</p>
      </div>
    </div>
    <fade-animation>
    <common-gallary :galleryObj="detailheader" v-show="showGallary" @close="closeGallary"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
   import  CommonGallary from 'common/gallary/Gallary'
   import FadeAnimation from 'common/fade/FadeAnimation'
    export default {
        name: "DetailBanner",
        components:{
          CommonGallary,
          FadeAnimation
        },
      props:{
        detailheader:Object
      },
      computed:{
        gallaryBanners:function () {
          return (this.detailheader.subImages || "").split(",");
        }
      },
      data(){
        return {
          showGallary:false
        }
      },
      methods:{
        handleClickBanner(){
          this.showGallary=true
        },
        closeGallary(){
          this.showGallary=false
        }
      }
    }
</script>

<style scoped lang="stylus">
  @import "~styles/mixins.styl"
 .banner
   position :relative
   overflow :hidden
   height :0
   padding-bottom :55%
   .banner-img
     width:100%
   .banner-info
     display :flex
     position: absolute
     left:0
     right:0
     bottom:0
     line-height :.6rem
     color: #ffffff
     min-width :0
     background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
     .banner-title
       flex:1
       ellipsis()
       font-size :.32rem
       padding: .2rem
     .banner-number
       margin-right :.1rem
       height :.2rem
       line-height :.2rem
       margin-top: .14rem
       border-radius :.1rem
       padding:0.1rem
       background:rgba(0,0,0,.8)
       font-size :.2rem
       .icon-text
         font-size :.2rem


</style>
